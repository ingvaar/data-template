$script = <<SCRIPT
echo "Installing venv..."
sudo apt update > /dev/null
sudo ln -s /usr/bin/python3 /usr/bin/python 1> /dev/null
sudo apt install python3-venv pkg-config build-essential python3-dev -y > /dev/null
echo "\njupyter() { if [[ \\$1 == \\"notebook\\" ]]; then command jupyter notebook --ip=0.0.0.0 \\${@:2}; else command jupyter \\${@:1}; fi; }\n" >> ~/.bashrc
echo "\ncd workspace && source env/bin/activate\n" >> ~/.profile

echo "Setting up venv..."
cd workspace
python -m venv env
source env/bin/activate
pip install jupyter 1> /dev/null

SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "bento/ubuntu-20.04" # 20.04 LTS

  config.vm.synced_folder "workspace", "/home/vagrant/workspace"

  config.vm.provision "shell", inline: $script, privileged: false

  # Expose port for jupyter notebook
  config.vm.network "forwarded_port", guest: 8888, host: 8888, auto_correct: true, host_ip: "127.0.0.1"
end
