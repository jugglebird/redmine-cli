require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "redmine-cli"
    gem.summary = %Q{Command-line interface for Redmine issues}
    gem.description = %Q{Command-line interface for Redmine issues}
    gem.email = "knoopx@gmail.com"
    gem.homepage = "http://github.com/knoopx/redmine_cli"
    gem.authors = ["Víctor Martínez"]
    gem.add_development_dependency "thoughtbot-shoulda", ">= 0"
    gem.add_dependency "optitron", "~> 0.1.8"
    gem.add_dependency "activeresource", "~> 2.3.5"
    gem.add_dependency "terminal-table", "~> 1.4.2"
    gem.add_dependency "rainbow", "~> 1.1"
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "redmine_cli #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
