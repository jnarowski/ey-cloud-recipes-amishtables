Memcached
===============

A chef recipe for configuring distributed memcached on [EY Cloud]. This recipe is meant to allow memcached to accept remote connections and add all the servers in your EY Cloud cluser to the `/data/<app_name>/shared/config/memcached.yml` file. 

To make use of this recipe you will also need to add a [deploy hook](http://docs.engineyard.com/use-deploy-hooks-with-engine-yard-appcloud.html) to your application to create a symlink for the memcached configuration. Just add a line like this to your `before_migrate.rb` hook:
    
    run "ln -nfs #{shared_path}/config/memcached_custom.yml #{release_path}/config/memcached.yml"
    

[EY Cloud]: https://cloud.engineyard.com/extras
