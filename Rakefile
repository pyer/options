# encoding: UTF-8

require 'rubygems'
require 'rubygems/package'
require 'rubygems/installer'
require 'rake'
require 'rake/clean'
$LOAD_PATH << 'lib/pyer'

spec = Gem::Specification.load('pyer-options.gemspec')
target = "#{spec.name}-#{spec.version}.gem"

desc 'Test and build'
task default: [:test, :build]

desc 'Test gem'
task :test do
  ruby 'test/test_banner.rb'
  ruby 'test/test_command.rb'
  ruby 'test/test_help.rb'
  ruby 'test/test_flag.rb'
  ruby 'test/test_value.rb'
end

desc 'Build gem'
task build: :clean do
  Gem::Package.build spec, true
end

desc 'Install gem'
task :install do
  gi = Gem::Installer.new target
  gi.install
end

CLEAN.include "#{spec.name}*.gem"
