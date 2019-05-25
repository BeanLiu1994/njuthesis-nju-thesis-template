
## 更新的方式：

sudo docker pull sumankhanal/texlive-2019
sudo docker run -it sumankhanal/texlive-2019 /bin/bash
ln /usr/local/texlive/2019/texmf-dist/fonts/opentype/public/fandol/ /usr/share/fonts/tlfonts-fandol -s
#ln /usr/local/texlive/2019/texmf-dist/fonts/type1/adobe/ /usr/share/fonts/tlfonts-adobe-vf -s
ln /usr/local/texlive/2019/texmf-dist/fonts/type1/urw/ /usr/share/fonts/tlfonts-urw-vf -s
fc-cache -fv

apt-get update
apt-get install git -y
git clone https://github.com/BeanLiu1994/njuthesis-nju-thesis-template -b travis_test
cd njuthesis-nju-thesis-template
xelatex -synctex=1 -interaction=nonstopmode -file-line-error sample.tex 
bibtex sample
xelatex -synctex=1 -interaction=nonstopmode -file-line-error sample.tex 
xelatex -synctex=1 -interaction=nonstopmode -file-line-error sample.tex 
