
================================
Ionic Template para Ubuntu 14.04
================================

Arquivos do vagrant para ambiente de desenvolvimento de projetos [ionic](http://ionicframework.com/).


Como usar:
-------------

Instale [virtualbox](http://www.virtualbox.org/)

Instale [vagrant](http://vagrantup.com/)

Instale o plugin [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) do vagrant

Instale [ansible](http://www.ansible.com/home)

Clone este repositório

Entre no diretorio do repositório, levante a box e acesse via ssh
```bash
    $ cd [repo]
    $ vagrant up --provision
    $ vagrant ssh -- -Y
```
Notas:
------
Adicionar as variáveis do android sdk ao bashrc local.
```bash
    $ cat bashrc >> ~/.bashrc
```
Rode o android e escolha qual sdk deseja instalar.
```bash
    $ android
```
Customize o Vagrantfile para ter acesso as portas usb.
```ruby    
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
```
Faça o [guide](http://ionicframework.com/docs/guide/) do ionic.
GET UP AND ENJOY.
