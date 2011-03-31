require 'rake/testtask'
require 'bundler'
Bundler::GemHelper.install_tasks

task :default => :test
task :spec    => :test

Rake::TestTask.new do |t|
  t.pattern = "spec/**/*_spec.rb"
end

desc "Run watchr"
task :watchr do
  sh %{bundle exec watchr .watchr}
end
task :w => :watchr

desc "Run the Application via Rack"
task :rackup do
  sh %{rackup config.ru}
end
task :r => :rackup

desc "Run the server using shotgun"
task :server do
  sh %{bundle exec shotgun --server=thin --port=9393 config.ru}
end
task :s => :server