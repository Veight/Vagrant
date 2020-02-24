Vagrant.configure("2") do |config|


# Run backup on both virtual machines: box1 and box2

  config.vm.provision "shell", path: "backup_script.sh"


  config.vm.dfine "box1" do |box1| ##ERROR: "dfine" doesn't exit! double-check spelling


       #box1.vm.provision "shell", inline: <<-SHELL
        #        sudo apt-get update

        #       SHELL

        box1.vm.box="ubuntu/trusty64"

        box1.vm.network :forwarded_port, guest: 22, host: 10124, id: "ssh"

        box1.vm.network :private_network, ip: "192.168.56.101"

        box1.vm.provider :virtualbox do |v|
        
  v.customize ["modifyvm", :id, "--memory", 1020]
       
       end

     end

  config.vm.dfine "box2" do |box2| ##ERROR: "dfine" doesn't exit!double-check spelling

        #box2.vm.provision "shell", path: "backup_script.sh"
                 #sudo apt-get install -y nginx

                 #SHELL


         box2.vm.box="ubuntu/xenial64"

         box2.vm.network :forwarded_port, guest: 22, host: 10223, id: "ssh"

         box2.vm.network :private_network, ip: "192.168.56.102"

      end

config.vm.dfine "box3" do |box3| ##ERROR: "dfine" doesn't exit! double-check spelling

        box3.vm.provision "shell", inline: <<-SHELL 
                 sudo apt-get install -y apache2

                 SHELL


         box3.vm.box="ubuntu/xenial64"

         box3.vm.network :forwarded_port, guest: 22, host: 10223, id: "ssh" ##ERROR: Host 10223 has been used. Use different host number

         box3.vm.network :private_network, ip: "192.168.56.103"

      end

end
