!SLIDE code smaller
# Przykłady #

    @@@ ruby

    def irb(from, to)
      kod_z_irb = `irb -f --inspect --prompt xmp 2>&1 < #{from}`
      przetworzony = kod_z_irb.
        split("\n").
          reject{|linia| linia.includes?("Switch to") }.
          map{|linia| linia.gsub(/^\s+==>/, "  #==>") }.
        join("\n")

      File.open(to, "w"){|f| f.write(przetworzony)}
    end

!SLIDE code smaller
# Przykłady #   

    @@@ ruby
    def dlugosc_filmu(sciezka)
      info = `mplayer -frames 0 -identify #{sciezka} 2>&1`
      dlugosc = info.split("\n").find{|linia| linia.includes?("ID_LENGTH") }
      sekund = dlugosc.split("=").last.to_i;
      "#{s/60}m #{s%60}s"
    end

    > puts dlugosc_filmu("x.avi")
    1m 30s
