ASSETS_DIR=assets
SOURCE_DIR=themes
DESTNN_DIR=$(HOME)/.config/terminology/themes

SRC_EXT=edc
OBJ_EXT=edj

BASE=$(ASSETS_DIR)/base.$(SRC_EXT)

OBJS=$(patsubst %.$(SRC_EXT), %.$(OBJ_EXT), $(wildcard $(SOURCE_DIR)/*.$(SRC_EXT)))

EDJE_CC=edje_cc
EDJE_CC_IMG_FLAGS=-id $(ASSETS_DIR)
EDJE_CC_SND_FLAGS=-sd $(ASSETS_DIR)
EDJE_CC_FLAGS=$(EDJE_CC_IMG_FLAGS) $(EDJE_CC_SND_FLAGS)

.PHONY: all clean install


all: $(OBJS)

%.$(OBJ_EXT): %.$(SRC_EXT) $(BASE)
	$(EDJE_CC) $(EDJE_CC_FLAGS) $< $@

clean:
	rm -f $(SOURCE_DIR)/*.$(OBJ_EXT)

install: $(OBJS)
	mkdir -p "$(DESTNN_DIR)"
	install -Dm644 $^ "$(DESTNN_DIR)"
