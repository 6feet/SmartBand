#TODO: make the device choice interactive:
MAC_ADDR = "C4:2A:69:B8:49:50"
DROP_DIR="~/Dropbox/firmware"

GIT_HASH=$$(git rev-parse --short HEAD)
DATE_TIME=$$(date +"%Y.%m.%d_%Ih%Mm%Ss")

BIN_DIR = /tmp/arduino_build

ELF = $(BIN_DIR)/*elf

GDB_SRV = JLinkGDBServer
ARM_GDB = arm-none-eabi-gdb

ARG = -if swd -speed 1000 -device NRF52832_xxAA

TERM = gnome-terminal --
BOARD = nRF52D6Fitness:nRF5:dsd6Watch:softdevice=onlySoftDevice

.PHONY: all BLE_upload dropbox upload compile pref_list debug startgdbserver \
		local_startgdbserver stopgdbserver clean clean_cache c l d


all: compile BLE_upload


BLE_upload:
	@echo "Using device with MAC address: $(MAC_ADDR) (see Makefile)"
	sudo ./desay_dfu.py	\
		-a $(MAC_ADDR) \
		-z $(BIN_DIR)*/*zip


dropbox: compile
	cp $(BIN_DIR)*/*zip $(DROP_DIR)/hash_$(GIT_HASH)_$(DATE_TIME).zip

# TODO: make install (upload could depend on it too) examples:
#
# Install AVR board support, 1.6.2
# arduino --install-boards "arduino:avr:1.6.2"
#
# Install Bridge and Servo libraries
# arduino --install-library "Bridge:1.0.0,Servo:1.2.0"


# Documentation:
# https://github.com/arduino/Arduino/blob/master/build/shared/manpage.adoc

upload: *.ino *.cpp *.h stopgdbserver clean_cache
	arduino  --pref build.path=$(BIN_DIR) --preserve-temp-files --board $(BOARD) \
			 --upload --verbose-upload --useprogrammer --verbose *.ino

# optional
compile: *.ino *.cpp *.h clean_cache
	arduino --pref build.path=$(BIN_DIR) --preserve-temp-files --board $(BOARD) \
			--verify --verbose *ino


# optional
pref_list:
	arduino --get-pref

# TODO: use precise ELF name
debug: $(ELF) startgdbserver
	$(ARM_GDB) $(ELF)

startgdbserver:
	@pidof $(GDB_SRV) > /dev/null || { $(TERM) $(GDB_SRV) $(ARG) & sleep 1 ; }

#optional
local_startgdbserver:
	@pidof $(GDB_SRV) > /dev/null || $(GDB_SRV) $(ARG)

stopgdbserver:
	@pidof $(ARM_GDB) > /dev/null && killall $(ARM_GDB) || true
	@pidof $(GDB_SRV) > /dev/null && killall $(GDB_SRV) || true

clean_cache:
	rm -rf /tmp/arduino_cache*

clean: clean_cache
	rm -rf $(BIN_DIR)

###############################################################################
# Lazy aliases:

c: compile

l: local_startgdbserver

d: debug

