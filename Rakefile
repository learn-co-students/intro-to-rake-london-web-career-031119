namespace :greeting do
desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end
  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end


namespace :db do
  desc 'migrate changes to your database'
  #You add this one first to create dependency.
  #Our underneath task (:migrate => :environment) need to have access to environment.rb
  #that's because Student.create_table code would require access to the config/environment.rb
  #file (which is where the student class and database are loaded).
  task :environment do
  require_relative './config/environment'
  end

  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end

end

desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end
