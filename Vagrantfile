# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "generic/ubuntu2004"
  N = 3

  (1..N).each do |i|
    # Defining VM properties
    config.vm.define "butovoboy_vm#{i}" do |node|
      node.vm.hostname = "butovoboy-vm#{i}"
      # Create a private network, which allows host-only access to the machine
      # using a specific IP.
      config.vm.network "private_network", type: "dhcp"
      node.vm.provider 'vmware_desktop' do |vb|
#        vb.name = "butovoboy-vm#{i}"
        vb.memory = 2048
        vb.cpus = 1
        vb.gui = false
      end
      # Specifying ansible playbook for every vagrant node
    end
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
#      ansible.groups = {
#        "gitlab" => ["butovoboy_vm1"],
#        "mattermost" => ["butovoboy_vm2"],
#        "redmine" => ["butovoboy_vm3"],
#        "all_groups:children" => ["gitlab", "mattermost", "redmine"]
#      }
  end
end
