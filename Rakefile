desc "Parse haml layouts"
task :parse_haml do
  print "Parsing Haml layouts..."
  system(%{
    cd _layouts/haml && 
    for f in *.haml; do [ -e $f ] && haml $f ../${f%.haml}.html; done
  })
  puts "done."
end

desc "Watch the site and regenerate when it changes"
task :watch_haml do
  require 'fssm'
  puts ">>> Watching for Changes <<<"
  FSSM.monitor("#{File.dirname(__FILE__)}/_layouts/haml", '*.haml') do
    update do |base, relative|
      puts "rebuilding #{relative}"
      system(%{
        cd _layouts/haml &&
        haml #{relative} ../#{relative.sub(/.haml$/, '.html')}
      })
    end
  end
end