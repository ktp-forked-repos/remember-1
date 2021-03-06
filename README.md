# remember
Collection of useful commands I always forget.

##### Parallelize a command in a nested bash for loop

    for dir in ~/example/*; do for image in $dir/*.png; echo $image & done; done

##### Resize all images in a folder with Image Magick
  
    for i in *.jpg; do convert $i -resize 500x $i; done

##### Install Terminator

    sudo add-apt-repository ppa:gnome-terminator
    sudo apt-get update
    sudo apt-get install terminator

##### Install NVidia Drivers

    sudo add-apt-repository ppa:xorg-edgers/ppa
    sudo apt-get update
    sudo apt-get install nvidia-367
  
##### Color Prompt with Git Branch

Inside .bashrc, use this :

    parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
    }
    if [ "$color_prompt" = yes ]; then
     PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
    else
     PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
    fi

to replace this:

    if [ "$color_prompt" = yes ]; then
        PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
    else
        PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
    fi

##### Monitor CPU Speed of All Cores

    watch -n.5 "cat /proc/cpuinfo | grep \"^[c]pu MHz\""
    
##### Delete all Docker containers

    docker rm $(docker ps -a -q) -f

##### Delete all Docker images
    
    docker rmi $(sudo docker images -aq)

##### Install Google Chrome

    wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
    sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
    sudo apt-get install -f
    google-chrome

##### Generate SSH Key
    
    ssh-keygen -t rsa -b 4096 -C "alexhagiopol@gmail.com"
    
##### Install SimpleScreenRecorder

    sudo add-apt-repository ppa:maarten-baert/simplescreenrecorder
    sudo apt-get update
    sudo apt-get install simplescreenrecorder
    
