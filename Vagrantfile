# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

path = "#{File.dirname(__FILE__)}"

unless File.exists?('server')
  p `git submodule init`
  p `git submodule update`
end

require 'yaml'
require path + '/server/infrastructure.rb'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  Infrastructure.configure(config, YAML::load(File.read(path + '/Infrastructure.yml')))
end
