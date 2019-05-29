source ENV['GEM_SOURCE'] || "https://rubygems.org"

def location_for(place, fake_version = nil)
  if place =~ /^((?:git|https?)[:@][^#]*)#(.*)/
    [fake_version, { :git => $1, :branch => $2, :require => false }].compact
  elsif place =~ /^file:\/\/(.*)/
    ['>= 0', { :path => File.expand_path($1), :require => false }]
  else
    [place, { :require => false }]
  end
end

gem 'rspec'
gem 'rspec_junit_formatter'
gem 'pupperware',
  :git => 'https://github.com/puppetlabs/pupperware.git',
  :ref => 'master',
  :glob => 'gem/*.gemspec'
