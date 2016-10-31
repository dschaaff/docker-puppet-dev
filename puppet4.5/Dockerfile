#########################################################
# Dockerfile to build container for running rspec tests
#########################################################
FROM ruby:2.1
MAINTAINER Daniel Schaaff 'daniel@danielschaaff.com'

# specify puppet version to install
ENV PUPPET_GEM_VERSION=4.5.2

# Add Gemfile
COPY Gemfile /tmp

RUN bundler install --gemfile /tmp/Gemfile

# variable for working directory
ENV module_dir /module

# mount the local module directory based on variable passed in
VOLUME ${module_dir}

# Our default command
CMD ["rm -rf Gemfile.lock && bundle exec rake spec"]
