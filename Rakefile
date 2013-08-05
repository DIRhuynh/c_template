require 'rake/clean'

CLEAN.include('obj/*.o')
CLOBBER.include('challenge.osx')

SRC = FileList['src/*.c']
OBJ = SRC.pathmap("obj/%f").ext('o')

INCLUDE="-Iinclude"
OPTIONS="-ansi -Wall -g"

task :default => ['challenge']

file 'challenge' => OBJ do
  sh "gcc #{OPTIONS} -o challenge.osx #{OBJ}"
end

#rule(/^obj\/*\.o$/ => [proc { |tn| tn.sub(/^obj/, 'src')}]) do |t|
rule '.o' => [proc { |tn| tn.sub(/\.o$/, '.c').sub(/^obj\//, 'src/') }] do |t|
  sh "gcc #{OPTIONS} #{INCLUDE} -c #{t.source} -o #{t.name}"
end

# File dependencies go here ...
file 'main.o' => ['main.c', 'globals.h']
file 'globals.o' => ['globals.c', 'globals.h']
file 'challenge.o' => ['challenge.c', 'challenge.h']
