Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end

  config.vm.define :renv do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RHEL8.8_base"
    server.vm.host_name = "renv.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_renv.yml"
#     ansible.playbook = "deploy_renvr_DEV.local.yml"
#     ansible.playbook = "deploy_renv_server_DEV.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.26"
    server.vm.network :private_network, ip: "192.168.56.129"
  end



#######################################################################################################################################

# config.trigger.before :destroy do |trigger|
#   run "rm -Rf /tmp/abc/*"
    # subscription-manager remove --all
    # subscription-manager unregister
    # subscription-manager clean
#   trigger.name = "Destroy Trigger ..."
#   trigger.info = "Destroy Trigger Execution ..."
#   trigger.run = { path: "subscription-manager remove --all"}
#   trigger.run = { path: "subscription-manager unregister"}
#   trigger.run = { path: "subscription-manager clean"}
# end
end
