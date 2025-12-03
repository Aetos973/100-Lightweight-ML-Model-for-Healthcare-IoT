.PHONY: env docker-build docker-run test clean

env:
	conda env create -f environment.yml || conda env update -f environment.yml
	echo "Activate with: conda activate ml-iomt-pipeline"

docker-build:
	docker build -t ml-iomt:latest .

docker-run:
	docker run -it --rm -v $(PWD):/app ml-iomt:latest $(CMD)

test:
	python -m pytest -q

clean:
	rm -rf artifacts/* data/staging/* data/clean/* __pycache__
