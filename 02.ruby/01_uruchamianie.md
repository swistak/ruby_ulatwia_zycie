!SLIDE commandline incremental
# Ruby z linii poleceń #

    @@@ shell
    $ ruby -e 'puts "Heja!"'
    Heja!
    $ ruby -e 'puts 2+5'
    7

!SLIDE commandline incrementala
## Operacje na strumieniach tekstowych ##

    @@@ shell
    $ cat lorem.txt
    >Lorem<
    >Ipsum<
    >Doles<

    $ ruby -n -e 'puts ">" + $_.strip + "<"' < lorem.txt
    >Lorem<
    >Ipsum<
    >Doles<
    
    $ ruby -n -e 'print $_ unless $_ =~ /orem/' < lorem.txt
    Ipsum
    Doles

!SLIDE commandline incremental

## Operacje na plikach ##

    @@@ shell
    $ ruby -e 'p ARGV' a.txt b.txt
    ["a.txt", "b.txt"]

    $ ruby -e 'ARGV.each{|f| puts 
      File.read(f).gsub("s", "$") }' lorem.txt
    Lorem
    Ip$um
    Dole$

!SLIDE code smaller
## Szablon kopiowania plików ##

    @@@ ruby
    pliki = ARGV
    pliki.each do |plik|
      zawartosc = File.read(plik)
      File.open("#{plik}.copy", w) do |wyjscie|
        # Tutaj robimy coś z zawartością
        wyjscie.print zawartosc
      end
      `mv '#{plik}.copy' '#{plik}'`
    end
