$script = <<SCRIPT
sudo apt-get install software-properties-common
sudo apt-add-repository -y ppa:ansible/ansible
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
sudo apt-get install -y ansible python-pip oracle-java8-installer
sudo pip install passlib
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "logstash" do |logstash|
  end

  config.vm.provider "virtualbox" do |v|
    v.linked_clone = true
  end

  config.vm.provision "shell", :inline => $script


  config.vm.provision "shell",
    :path => "vagrant_specs.sh",
    :upload_path => "/home/ubuntu/specs",
    # change role name below
    :args => "--install ansible-logstash"
end
