SUMMARY
---

This project creates a machine, `alpha`, running the Foreman. It
serves out the config from the sub-directory `puppet-config`.


HOWTO
---

1. Install VirtualBox.

2. Download http://www.packer.io and add the binaries to your PATH.

3. Install vagrant. **For CentOS 7 NFS support, you need to be using
   Vagrant > 1.6.5.**

        # This should get you started:
        git clone https://github.com/mitchellh/vagrant
		bundle install
		sudo gem install

4. `make`

5. Clone the puppet repo that you want to work on into `puppet-config` e.g.

        git clone https://github.com/BorwickAtVT/puppet-config

6. `vagrant up`. **Note: each file in `puppet-config` is symlinked to
   alpha:/etc/puppet when `vagrant up` is run. Therefore, if you add a
   new file it won't get symlinked unless you do so manually.

7. If needed, you can run `make clean`. (Note this is more like a
   "distclean" and will wipe everything except ISO downloads.)

UPDATING
---

If you're using a previous version and are ready to erase what you've
been working on, run `make clean`.

CREDITS
---

https://github.com/douglaswth/dt-freebsd-packer/ was extremely
helpful!

http://blog.codeship.io/2013/11/07/building-vagrant-machines-with-packer.html

https://github.com/gwagner/packer-centos/blob/master/http_directory/anaconda-ks.cfg
