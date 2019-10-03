Requirments : 
1. Python 2.6 atau diatasnya 
2. socat
3. psutil
4. hglib
5. pygit2 atau git  
6. bzr 
7. pyuv 
8. i3ipc
9. xrandr 


Tahapan install : 
1. Install pip (slpkg -s slonly pip)
2. Install powerline
   - git clone https://github.com/powerline/powerline 
   - cd powerline
   - python setup.py install; ATAU python3 setup.py install; JIKA TIDAK BERHASIL pip install powerline-status
   - cd fonts 
   - mv PowerlineSymbols.otf /usr/share/fonts/OTF/ 
   - mv 10-powerline-symbols.conf .config/fontconfig/conf.d/
   - fc-cache -vf /usr/share/fonts/OTF/ 
   - cd ../.. 
   - rm -rf powerline JIKA INGIN DIHAPUS
3. Install patch-fonts for powerline
   - git clone https://github.com/powerline/fonts.git --depth=1
   - cd fonts
   - ./install.sh
   - cd ..
   - rm -rf fonts JIKA INGIN DIHAPUS 
   - (Ubah font Terminal yang gunakan menggunakan salah satu patch-fonts for powerline. Nama-namanya bisa dilihat di https://github.com/powerline/fonts)
4. Ubah bahasa sistem menggunakan en_US.UTF-8 (support unicod/untuk symbol)
   - vim /etc/profile.d/lang.sh 
   - (beri  # didepan export LANG=en_US)
   - (hapus # didepan export LANG=en_US.UTF-8)
5. Aktifkan powerline 
   - pip show powerline-status (perhatikan bagian Location : ) 
   - vim .bashrc 
     powerline-daemon -q
     POWERLINE_BASH_CONTINUATION=1
     POWERLINE_BASH_SELECT=1
     . /usr/local/lib/python2.7/dist-packages/powerline/bindings/bash/powerline.sh
   - (ganti bagian) /usr/local/lib/python2.7/dist-packages/ (dengan yang muncul di Location :)
   - (Tutup terminalnya kemudian dibuka kembali, atau restart)

REFERENSI : 
- https://www.tecmint.com/powerline-adds-powerful-statuslines-and-prompts-to-vim-and-bash/
- https://powerline.readthedocs.io/en/latest/installation.html
- https://github.com/powerline/fonts
- https://docs.slackware.com/slackware:localization

MASALAH : 
- Setelah upgrade phyton muncul error pada saat running powerline di terminal. 
  Solusinya install ulang powerlinenya, karena kemungkinan pada saat upgrade powerlinenya juga ikut terhapus,diketahui dari, saat jalankan perintah 'pip show powerline-status' tidak ada yang muncul. 
- Powe
