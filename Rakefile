namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end
  task :hola do
    puts 'hola de Rake!'
  end
end

desc 'loads dependencies and initialises environment'
task :environment do
  require_relative './config/environment'
end

desc 'drop into Pry terminal'
task :console => :environment do
  Pry.start
end

namespace :db do

  desc 'push changes to your database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed database with test data'
  task :seed do
    require_relative './db/seeds.rb'
  end

end
