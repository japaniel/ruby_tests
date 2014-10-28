#!/usr/bin/env ruby

@app_dir = File.join(ENV['HOME'], "test_apps")
@rails_dir = "trails"

task :default do
	puts "\n\nSo you think your Kung fu is pretty good ehh?\nI want to test your Ruby.\nMe against you...\nLETS KUNG FU!\n\n"
end

desc 'Can make a dir'
task :it_makes_a_dir do
	mkdir_p @app_dir
end	

desc 'Checks for gems'
task :check_for_gem, :gem do |task, args|
	begin
		gem "#{args[:gem]}"
	rescue LoadError
		puts "Don't gots no, #{args[:gem]}"
	end
end

desc 'Build a Rails app'
task :init_rails_app do
	cd @app_dir
    sh "rails new #{@rails_dir}"
end

desc 'Cleanerific'
task :clean do
	rm_rf @app_dir
end

desc 'All the things #SAFETYNET'
task :all => [:default, :it_makes_a_dir, :check_for_gem, :init_rails_app]
