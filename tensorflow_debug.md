### tensorflow_debug

* Din-seq模型中遇到的问题
  * tf.shape(tensor) 可以获得tensor的shape,在有数据流时获取, 而tensor.get_shape().as_list()直接获得, 如果没有数据流可能获得None,
  * 在embedding_lookup中设置默认值,使用 封装好的api即可. Tf.nn.safe_embedding_lookup_sparse_hashtable_v2中serving_default_value=np.zeros(embedding_size, dtype=float), 而tf.nn.embedding_lookup_hashtable_v2中serving_default_value=tf.constant(params["v_default_value"],dtype=tf.float32)
  * 传入特征时要在load_data中定义, 不要重复定义
  * 全连接层fully_connected输入时要注意输入tensor最后一维维度, 不能是None或者?
  * fully_connected可以使用weights_regularizer设置tf.contrib.layers.l2_regularizer(0.00001)加入l2正则项