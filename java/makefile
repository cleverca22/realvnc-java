# Makefile for building java vncviewer using jikes and GNU make.  This makefile
# probably won't work for you!
#

JAVAC = jikes -classpath .:$$CLASSPATH
JAR = jar
INSTALL_DIR = ../unix/java
SRCS = $(shell find . -name '*.java' -print 2>/dev/null)

all:: vncviewer.jar install

vncviewer.jar: $(SRCS)
	$(RM) `find . -name '*.class' -print`
	$(JAVAC) -d . $^
	$(JAR) cmf manifest $@ `find . -name '*.class' -print`

clean::
	$(RM) `find . -name '*.class' -print`
	$(RM) vncviewer.jar

install:
	if [ -d $(INSTALL_DIR) ]; then \
	  cp -pf index.vnc vncviewer.jar logo150x150.gif $(INSTALL_DIR); \
	fi
