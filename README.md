openshift-papertrailapp-cartridge
=================================

####This only works on non-scaled gears at the moment

Add an environment variable for your papertrailapp port number:

    rhc set-env PAPERTRAILAPP_PORT=<port> PAPERTRAILAPP_HOST=<host_as_ip_address> -a <appname>

Where <port> is your papertrailapp port number, and <appname> is the name of your application.
Then restart your application

    rhc app restart <appname>
    
Then install this cartridge

    rhc cartridge-add https://raw.github.com/developercorey/openshift-papertrailapp-cartridge/master/metadata/manifest.yml -a <appname>
    
This cartridge will monitor the files in all log directories that are published as environment variables, and exist.
You can ssh into your gear and run the following command to see what directories will be monitored

    env | grep LOG
    
Please log any issues to the git repository issue tracker
