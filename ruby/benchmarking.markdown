Benchmarking in Ruby
====================
Bencharmking snippets of code in Ruby to compare relative execution speeds
isn't difficult - simply call `#report` inside a `Benchmark::bm` block, as
follows:
    
    require 'benchmark'
    Times = 10_000_000
    
    def thrice_yield
      3.times { yield }
    end
    
    def thrice_block &block
      3.times &block
    end
    
    def thrice_proc_dot_new
      3.times &Proc.new
    end
    
    print "        " # Prettiness :3
    
    Benchmark.bm do |bm|
      bm.report "yield" do
        Times.times do
          thrice_yield { :foo }
        end
      end
      
      bm.report "block" do
        Times.times do
          thrice_block { :foo }
        end
      end
      
      bm.report "Proc.new" do
        Times.times do
          thrice_proc_dot_new { :foo }
        end
      end
    end
    
The results will look something like this:
    
                  user     system      total        real
       yield 16.860000   0.110000  16.970000 ( 18.369037)
       block 40.110000   0.290000  40.400000 ( 43.453339)
    Proc.new 37.430000   0.250000  37.680000 ( 40.708240)
    
