# MacOSX PHP Gettext Extension Install

## MacOSX Mojave Install Instructions

- clone the repository or download the the file named "gettext.so"
- copy the file into /usr/lib/php/extensions/no-debug-non-zts-20160303
- add the following lines into /etc/php.ini so the modules get loaded:

    extension_dir = /usr/lib/php/extensions/no-debug-non-zts-20160303/
    extension = gettext.so

- test the installation:

    $ php -a
    Interactive shell
    
    php > echo gettext("Sample Text");
    Sample Text
    php > 

### Compile from source
    phpize
    export CFLAGS="-arch x86_64 -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include/php/main/ -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include/php/zend/ -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include/php/ -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include/ -I/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.14.sdk/usr/include/php/TSRM/"
    export LDFLAGS="-arch x86_64"
    ./configure
    make
    sudo make install
then do the configuration changes described above in php.ini

