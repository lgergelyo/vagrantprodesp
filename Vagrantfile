Vagrant.configure("2") do |config|
  
  config.vm.synced_folder ".", "/vagrant"


  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
  end

  config.vm.define "rancher" do |rancher|	
    config.vm.box = "centos/7"
    rancher.vm.hostname = "rancher"
    rancher.vm.network "public_network", bridge: "eno1", ip: "192.168.1.22", hostname: true
    rancher.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook.yml"
    end
  end

  # config.vm.define "k8s1" do |k8s1|
  #   config.vm.box = "centos/7"
  #   k8s1.vm.hostname = "k8s1"
  #   k8s1.vm.network "public_network", bridge: "wlp3s0", ip: "192.168.1.23", hostname: true
  # end

  # config.vm.define "k8s2" do |k8s2|
  #   config.vm.box = "centos/7"
  #   k8s2.vm.hostname = "k8s2"
  #   k8s2.vm.network "public_network", bridge: "wlp3s0", ip: "192.168.1.24", hostname: true
  # end

  # config.vm.define "k8s3" do |k8s3|
  #   config.vm.box = "centos/7"
  #   k8s3.vm.hostname = "k8s3"
  #   k8s3.vm.network "public_network", bridge: "wlp3s0", ip: "192.168.1.25", hostname: true
  # end

  # config.vm.define "ansible" do |ansible|
  #   config.vm.box = "centos/7"
  #   ansible.vm.hostname = "ansible"
  #   ansible.vm.network "public_network", bridge: "wlp3s0", ip: "192.168.1.26", hostname: true
  #   ansible.vm.provision "shell", 
  #     inline: <<-SHELL
  #     sudo yum install -y software-properties-common 
  #     sudo yum install epel-release -y
  #     sudo yum install ansible -y
  #     SHELL
  # end

  #  config.vm.provision "shell", inline: <<-SHELL
  #    sudo yum update -y
  #    sudo yum upgrade -y
  #  SHELL
end
