SOURCE=basic modern animation nonblock  xkcd
LIB=libplt_examples.a
build_dir=examplesbin
lflags=-L$(LPYTHONHOME)/config-3.8-x86_64-linux-gnu -lpython$(version)
incflags=-I$(PYTHONHOME) -I./
all: $(SOURCE) $(LIB)

.PHONY: $(SOURCE) 
source: $(SOURCE) $(patsubst %,%.o, $(SOURCE))

$(build_dir):
	mkdir $@
$(SOURCE): $(Build_dir) 
ifndef compile
	g++ -c $@.cpp $(incflags) $(lflags) -o examplesbin/$@.o
else
	g++  $@.cpp $(incflags) $(lflags) -o examplesbin/$@
endif

$(LIB): $(SOURCE)
	ar rcs $@ $(patsubst %,$(build_dir)/%.o, $(^)) || true
clean_obj: 
	rm -rf $(build_dir)*.o || true
clean:
	rm -rf $(build_dir)/*.o || true
	rm -rf *.a || true
	#rm -rf $(build_dir)/$(patsubst %, $(build_dir)/%.o, SOURCE) || true
