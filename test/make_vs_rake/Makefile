.PHONY : rm_middle build clean touchb

default: mf_d.tmp

mf_a.tmp: 
	@echo "filetask a"

mf_b.tmp: mf_a.tmp
	@echo "filetask b"

mf_c.tmp: mf_b.tmp
	@echo "filetask c"

mf_d.tmp: mf_c.tmp
	@echo "filetask d"

clean:
	rm mf_[a-z].tmp

build:
	touch mf_a.tmp
	touch mf_b.tmp
	touch mf_c.tmp
	touch mf_d.tmp

rm_middle:
	rm mf_[bc].tmp

touchb:
	touch mf_b.tmp
