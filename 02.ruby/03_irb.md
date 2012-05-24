!SLIDE code smaller
# Tryb interaktywny #

    @@@ ruby
    2+3
    # => 5
    3**5
    # => 243
    puts "* " * 20
    # * * * * * * * * * * * * * * * * * * * * 
    # => nil

!SLIDE code smaller
# Używanie poprzedniej wartości #

    @@@ ruby
    pozyczka = 1000
    # => 1000
    oprocentowanie = 0.5
    # => 0.5
    pozyczka * oprocentowanie
    # => 500.0
    _ + pozyczka
    # => 1500.0

!SLIDE code smaller
# Definiowanie metod #

    @@@ ruby
    def koszt(kwota, procent_rocznie, miesiecy)
      pr = 1.0 * procent_rocznie * miesiecy / 12 / 100
      kwota * pr
    end
    # => nil
    koszt(1000, 12, 2)
    # => 20.0
    koszt 10000, 24, 36
    # => 7200.0
