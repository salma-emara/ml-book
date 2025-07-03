# ml-book

If you are trying to build the book locally, you can follow the instructions below.

1- Clone this GitHub repo. In your terminal, type the following command:

git clone https://github.com/salma-emara/ml-book/
cd ml-book

2- Install jupyter-book and other dependencies by running the following command in the terminal

```
pip install -r requirements.txt
```

3- To build everything for the first time 

```
jupyter-book build --all textbook
```
and to build after updating a markdown file:
```
jupyter-book build textbook
```

4- To view the book, you have two options:

To open directly, type the following command in the terminal:

```
open textbook/_build/html/index.html
```

To know more, 

[Tutorials](https://jupyterbook.org/en/stable/start/create.html)


