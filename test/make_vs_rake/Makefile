.PHONY : rm_middle build clean touchb

default: mf_d

mf_a: 
	@echo "filetask a"

mf_b: mf_a
	@echo "filetask b"

mf_c: mf_b
	@echo "filetask c"

mf_d: mf_c
	@echo "filetask d"

clean:
	rm mf_[a-z]

build:
	touch mf_a
	touch mf_b
	touch mf_c
	touch mf_d

rm_middle:
	rm mf_[bc]

touchb:
	touch mf_b
