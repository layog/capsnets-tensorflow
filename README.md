# capsnets-tensorflow
Implementation of Capsule networks (With Dynamic Routing Algorithm) based on Aurélien's implementation 

### Original notebooks and videos
* [Jupyter Notebook](https://github.com/ageron/handson-ml/blob/master/extra_capsnets.ipynb)  
* [Capsule Network Explanation](https://www.youtube.com/watch?v=pPN8d0E3900)
* [Implementation Explanation](https://www.youtube.com/watch?v=2Kawrd5szHE)

### Improvements
* The `Dynamic Routing Algorithm` is implemented in the original notebook without a loop and by creating new operations in the graphs. This limits the use of the routing algorithm as (I've changed it to use `tf.while_loop`)
	1. We cannot dynamically increase the number of routing loops
	1. Takes up much more space in the GPU  
* In the Aurelien's notebook, many times `tile` function is used, which is not very efficient and hence I've replaced it with `einsum`

---
#### Installation
(Run the following in a `python=2.7` environment, although should work on `python3` as well, but I have not tested it yet)
* `pip install -r requirements.txt`
* (Optional) `python -m ipykernel install --user --name <desired-kernel-name>`

#### Evaluating the notebooks
* You can download the final tensorflow saver files from [here](https://drive.google.com/open?id=1cXxKRFzihE0A5Cz0w0ts3QMx39mBK8OY). Keep the files in the root directory of the project and skip the training block in the notebook (for evaluation).
* Or, just run the complete notebook which will train the network as well
> If you are using the latest tensorflow (`1.5.0`), you will encounter some warnings (regarding some argument deprecation). They won't break anything for now.