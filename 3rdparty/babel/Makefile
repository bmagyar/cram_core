
all: installed

TARBALL=babel-20110210.tar.bz2
TARBALL_URL=http://ai.uni-bremen.de/public/$(TARBALL)

downloaded: Makefile
	make clean
	$(shell echo $$ROS_ROOT)/core/rosbuild/bin/download_checkmd5.py $(TARBALL_URL) $(TARBALL)
	mkdir -p asdf
	touch rospack_nosubdirs
	touch downloaded

unpacked: downloaded
	tar xvjf $(TARBALL)
	touch unpacked

installed: unpacked
	ln -s ../babel/babel.asd asdf/babel.asd
	ln -s ../babel/babel-streams.asd asdf/babel-streams.asd
	touch installed

clean:
	rm -rf babel asdf $(TARBALL)
	rm -f downloaded rospack_nosubdirs installed unpacked
