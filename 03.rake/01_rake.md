!SLIDE code smaller
## Podstawy definiowania zadań ##

    @@@ ruby
    namespace "foo" do
      desc "Opis zadania" 
      task "bar" do
        puts "foo"
      end
    end

    @@@ shell
    rake foo:bar --trace

!SLIDE code smaller

## Zależności pomiędzy zadaniami ##

    @@@ ruby
    task "raz" do                                                                                                   
      puts "raz"                                                                                                    
    end 
 
    task "dwa" do                                                                                                   
      puts "dwa"                                                                                                    
    end
 
    task "trzy" => ["dwa", "raz"] do                                                                                
      puts "trzy"                                                                                                   
    end    
 
    task "cztery" => ["trzy", "raz"] do                                                                             
      puts "cztery"
    end
