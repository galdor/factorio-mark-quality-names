MOD_VERSION = $(shell <info.json jq -r .version)
MOD_NAME = $(shell <info.json jq -r .name)

MOD_FILES  = LICENSE
MOD_FILES += changelog.txt
MOD_FILES += $(wildcard *.json)
MOD_FILES += $(wildcard *.lua)

PKG_DIR = $(MOD_NAME)
PKG_NAME = $(MOD_NAME)_$(MOD_VERSION).zip

all: $(PKG_NAME)

clean:
	$(RM) $(wildcard *.zip)

$(PKG_NAME): $(MOD_FILES) GNUmakefile
	rm -rf $(PKG_DIR)
	mkdir -p $(PKG_DIR)
	cp $(MOD_FILES) $(PKG_DIR)/
	zip -r $(PKG_NAME) $(PKG_DIR)

.PHONE: all clean
