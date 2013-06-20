require 'rubygems'
require 'rake'



#############################################################################
#
# Helper functions
#
#############################################################################

def git_clean?
  git_state = `git status 2> /dev/null | tail -n1`
  clean = (git_state =~ /working directory clean/)
end

task :check_git do
  unless git_clean?
    puts "Dirty repo - commit or discard your changes and run deploy again"
    exit 1
  end
end

desc "Deploy to remote origin"
task :deploy => [:check_git] do
  source_branch = 'master'
  deploy_branch = 'gh-pages'
  message = "Site updated at #{Time.now.utc}"

  system "bundle exec jekyll build"
  system "git checkout \"#{deploy_branch}\""
  system "cp -r _site/* . && rm -rf _site/"

  unless git_clean?
    system "git add . && git commit -m \"#{message}\""
    system "git push origin \"#{deploy_branch}\""
    puts "Pushed to origin with commit message: #{message}"
  else
    puts "No changes to deploy - canceled"
  end

  system "git checkout \"#{source_branch}\""
end


#############################################################################


def git_clean?
  git_state = `git status 2> /dev/null | tail -n1`
  clean = (git_state =~ /working directory clean/)
end

task :check_git do
  unless git_clean?
    puts "Dirty repo - commit or discard your changes and run deploy again"
    exit 1
  end
end

desc "Sync with remote origin"
task :sync => [:check_git] do
  source_branch = 'master'
  deploy_branch = 'gh-pages'
  message = "Site synced at #{Time.now.utc}"

  system "bundle exec jekyll build"
  system "git checkout \"#{deploy_branch}\""
  system "cp -r _includes/* . && cp -r _layouts/* . && cp -r _posts/* . && cp -r _site/* . && rm -rf _site/"

  unless git_clean?
    system "git add . && git commit -m \"#{message}\""
    system "git push origin \"#{deploy_branch}\""
    puts "Pushed to origin with commit message: #{message}"
  else
    puts "No changes to deploy - canceled"
  end

  system "git checkout \"#{source_branch}\""
end






