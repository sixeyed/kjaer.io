require 'html-proofer'

task :test do
  options = { 
    :assume_extension => true,
    :check_favicon => true,
    :disable_external => true, # temporary
    :check_opengraph => false, # temporary
    :check_html => false, # temporary
    :external_only => true, # temporary
    :http_status_ignore => [429],
    :only_4xx => true,
    :internal_domains => [
      'kjaer.io',
      'kjaermaxi.me'
    ],
    :cache => {
      :timeframe => '6w'
    },
    :parallel => {
      :in_processes => 2
    },
    :verbose => true
  }

  begin
    HTMLProofer.check_directory("./_site", options).run
  rescue => msg
    puts "#{msg}"
  end
end