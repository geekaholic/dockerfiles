FROM debian:wheezy
MAINTAINER Bud Siddhisena "bud@geekaholic.org"

# Install dependencies
RUN apt-get update && apt-get install -y \
    git-core curl vim build-essential libssl-dev libcurl4-openssl-dev libreadline-dev \
    libxml2-dev libxslt1-dev libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Setup rbenv
RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv && \
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc && \
    echo 'eval "$(rbenv init -)"' >> ~/.bashrc && \
    mkdir -p ~/.rbenv/plugins && \
    git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build && \
    git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

CMD ["/bin/bash"]
