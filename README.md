# Pesetacoin Core [PTC] 0.9.2
==========================
PesetaCoin integration/staging tree
================================

http://www.pesetacoin.info

Copyright (c) 2009-2013 Bitcoin Developers<br />
Copyright (c) 2011-2013 Litecoin Developers<br />
Copyright (c) 2014-2018 PesetaCoin Developers


Que es PesetaCoin?
----------------
ESPECIFICACIONES

- Algoritmo Scrypt (POW)
- Número total de monedas: 166,386,000 PTCs 
- 166(.386) monedas por bloque (nueva tabla de recompensas)
- Block target: 1 minuto 
- Con soporte para Merged Mining
- RPC Port: 16638
- P2P Port: 16639

Recompensa
----------------------------------

    0 - 525,599:          166.386 PTC
    525,599 - 549,999:     83.193 PTC
    550,000 - 1,051,199:   50 PTC
    1,051,200 - 1,576,799: 25 PTC
    1,576,800 - 2,627,999: 10 PTC
    2,628,000 - 8,409,599:  5 PTC
    8,409,600+: 0 PTC
    
Compilación sin entorno gráfico:
----------------------------------

 
Instalar dependencias, clonar repositorio y compilar: 

	sudo apt-get update
	sudo apt-get install build-essential libtool autotools-dev autoconf pkg-config libssl-dev libboost-all-dev libminiupnpc-dev git libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev libdb++-dev
	git clone https://github.com/FundacionPesetacoin/Pesetacoin-0.9.2-Oficial.git
	cd Pesetacoin-0.9.2-Oficial/
	./autogen.sh
	./configure --with-incompatible-bdb
	make
	make install
	make-qt4 -makefile -Wall USE_QRCODE=1
	make 
 
	

Compilación con entorno gráfico:
----------------------------------

ejecutar:
 
	qmake-qt4 -makefile -Wall USE_QRCODE=1
	make 



License
-------

PesetaCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Pesetacoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly to indicate new official, stable release versions of Pesetacoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./pesetacoin-qt_test

