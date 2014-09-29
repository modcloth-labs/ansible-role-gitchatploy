# vim:filetype=ruby

Vagrant.configure('2') do |config|
  config.vm.box = 'modcloth/trusty64'

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'example.yml'
    ansible.sudo = true
    ansible.verbose = 'vvvv'
    ansible.extra_vars = {
      ssh_user: 'vagrant',
      hostname: 'vagrant-ubuntu-trusty-64.demo.modcloth.com',
    }

    if ENV['ANSIBLE_RAW_ARGUMENTS']
      ansible.raw_arguments = %W(#{ENV['ANSIBLE_RAW_ARGUMENTS']})
    end
  end
end
