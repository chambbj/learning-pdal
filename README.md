# learning-pdal

The purpose of this repository is to provide instructions as to how one can get started running PDAL within a Jupyter notebook.

# Getting Started

## Initialize and Update Data Submodule

```bash
$ cd notebooks/data
$ git submodule init
$ git submodule update
```

## Pulling the Image

```bash
$ docker pull chambbj/learning-pdal
```

## Rebuilding the Image

Not necessary if you have pulled the image from Docker Hub. Perhaps useful if you've made changes to the Dockerfile.

```bash
$ docker build -t learning-pdal .
```

## Running the Container

By default, the notebooks folder in this repository will be accessible within Jupyter, and one can work through all of the tutorials in this manner.

```bash
$ docker run -t --name learning-pdal -p 8888:8888 chambbj/learning-pdal
```

If you would like to modify and save any changes to your notebooks, you'll need to mount a volume, mapping a local path to the container.

```bash
$ docker run -t --name learning-pdal -v $(pwd)/notebooks/:/notebooks -p 8888:8888 chambbj/learning-pdal
```

In both instances, we expose port 8888. Jupyter is accessible at http://localhost:8888. A token will also be generated when Jupyter first starts, and this will be required for subsequent access.
