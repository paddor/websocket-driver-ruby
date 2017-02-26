require 'rubygems/package_task'

spec = Gem::Specification.load('websocket-driver.gemspec')

Gem::PackageTask.new(spec) do |pkg|
end

if RUBY_PLATFORM =~ /java/
  require 'rake/javaextensiontask'
  Rake::JavaExtensionTask.new('websocket_driver', spec) do |ext|
    ext.name = 'websocket_driver'
  end
else
  require 'rake/extensiontask'
  Rake::ExtensionTask.new('websocket_driver', spec) do |ext|
    ext.name = 'websocket_driver'
  end
end

task :clean do
  Dir['./**/*.{bundle,jar,o,so}'].each do |path|
    puts "Deleting #{path} ..."
    File.delete(path)
  end
  FileUtils.rm_rf('./pkg')
  FileUtils.rm_rf('./tmp')
end
