SOURCE=basic modern animation nonblock  xkcd
lflags=-L$(LPYTHONHOME)/config-3.8-x86_64-linux-gnu -lpython$(version)
incflags=-I$(PYTHONHOME) -I./
all: $(SOURCE)

.PHONY: $(SOURCE)
source: $(SOURCE) $(patsubst %,%.o, $(SOURCE))
$(SOURCE): 
	g++ $@.cpp $(incflags) $(lflags) -o $@


