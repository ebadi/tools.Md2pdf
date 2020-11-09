FROM ubuntu:20.04
MAINTAINER Fiware ULPGC <fiware@ulpgc.es>


RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update

RUN apt-get install texlive-xetex texlive-fonts-recommended texlive-latex-extra texlive -y
RUN apt-get install unzip git python3 python3-pip wget build-essential -y
RUN apt-get install pdftk -y

RUN wget https://github.com/jgm/pandoc/releases/download/1.15.1/pandoc-1.15.1-1-amd64.deb && dpkg -i pandoc-1.15.1-1-amd64.deb

RUN git clone https://github.com/ebadi/tools.Md2pdf.git &&  cd tools.Md2pdf && python3 setup.py install


ENTRYPOINT ["markdown_to_pdf"]

#CMD ["--help"]


# sudo docker build -t m2pdf-docker .
# docker run -v=/home/wave/carla:/md2pdf fiware/md2pdf -i /md2pdf/mkdocs.yml -o /md2pdf/documentation.pdf

