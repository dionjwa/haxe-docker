$script = <<SCRIPT
#Install nodejs+npm
curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -
sudo apt-get install -y nodejs
#Install docker
curl -sSL https://get.docker.com/ubuntu/ | sudo sh
#Expose docker remote API
echo 'DOCKER_OPTS="-H tcp://0.0.0.0:2376 -H unix:///var/run/docker.sock"' | sudo tee -a /etc/default/docker
sudo service docker restart
SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "phusion/ubuntu-12.04-amd64"
    config.vm.hostname = "haxe-docker-test"
    config.vm.provision "shell", inline: $script
end

