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
    
!SLIDE code smaller
## Szablon kopiowania plików z obsługą błedów ##

    @@@ ruby
    pliki = ARGV
    begin
      pliki.each do |plik|
        zawartosc = File.read(plik)
        File.open("#{plik}.copy", w) do |wyjscie|
          raise("Coś poszło nie tak") unless wszystko_ok
        end
      end

      pliki.each do |plik|
       `mv '#{plik}.copy' '#{plik}'`
      end
    rescue RuntimeError => e
      puts "Nastąpił błąd podczas przetwarzania polecenia"
    end
