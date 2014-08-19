
================================
Ionic Template para Ubuntu 14.04
================================

Arquivos do vagrant para ambiente de desenvolvimento do [ionic](http://ionicframework.com/).


Como usar:
-------------

Instale [virtualbox](http://www.virtualbox.org/)

Instale [vagrant](http://vagrantup.com/)

Instale o plugin [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) do vagrant

Instale [ansible](http://www.ansible.com/home)

Clone esse repositório

Entre no diretorio do repositório, levante a box e acesse via ssh

    $ cd [repo]
    $ vagrant up --provision
    $ vagrant ssh -- -Y

Notas:
------
Adicionar as variáveis do android sdk ao bashrc local.
    $ cat bashrc >> ~/.bashrc

Rode o android e escolha qual sdk deseja instalar.
    $ android

Customize o vagrant file para ter acesso a sua usb.
    Vagrant.configure("2") do |config|
      ...
      config.vm.provider "virtualbox" do |vb|
        ...
        vb.customize ["modifyvm", :id, "--usb", "on"]
        vb.customize ["usbfilter", "add", "0", "--target", :id, "--name", "android", "--vendorid", "######"]
        ...
      end
      ...
    end

Faça o [guide](http://ionicframework.com/docs/guide/), get up and enjoy.
