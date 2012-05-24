!SLIDE commandline incremental
# Ruby z linii poleceń #

    @@@ shell
    $ ruby -e 'puts "Heja!"'
    Heja!
    $ ruby -e 'puts 2+5'
    7

!SLIDE commandline incremental smaller
## Operacje na strumieniach tekstowych ##

    @@@ shell
    $ cat lorem.txt
    Lorem
    Ipsum
    Doles

    $ ruby -n -e 'puts ">" + $_.strip + "<"' < lorem.txt
    >Lorem<
    >Ipsum<
    >Doles<
    
    $ ruby -n -e 'print $_ if $_.includes?("psum")' < lorem.txt
    Ipsum

!SLIDE commandline incremental smaller

## Operacje na plikach ##

    @@@ shell
    $ ruby -e 'p ARGV' a.txt b.txt
    ["a.txt", "b.txt"]

    $ ruby -e 'ARGV.each do |f| \
        puts File.read(f).gsub("s", "$") \
      end' lorem.txt

    Lorem
    Ip$um
    Dole$

