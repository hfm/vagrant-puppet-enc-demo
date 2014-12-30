# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hfm4/centos6"
  config.vm.hostname = "enc.test.vag"

  config.vm.provision :shell do |install_puppet|
    install_puppet.inline = <<-'SCRIPT'
      require_version='3.7.3'
      puppet_version=$(rpm -q --queryformat '%{VERSION}' puppet)
      [ "$puppet_version" = "$require_version" ] || {
          rpm --import http://yum.puppetlabs.com/RPM-GPG-KEY-puppetlabs
          rpm -ivh http://yum.puppetlabs.com/puppetlabs-release-el-6.noarch.rpm
          yum install -y "puppet-${require_version}"
      }
    SCRIPT
  end

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "."
    puppet.manifest_file  = "init.pp"
    puppet.options = []
    puppet.options << "--node_terminus=exec"
    puppet.options << "--external_nodes=/vagrant/enc"
  end
end
