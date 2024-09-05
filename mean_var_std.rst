.. code:: ipython3

    from pprint import pprint

.. code:: ipython3

    import numpy as np

.. code:: ipython3

    def calculate(arr):
        if len(arr) != 9:
            raise ValueError("List must contain nine numbers.")
    
        m = np.array(arr).reshape([3, 3])
        r = {
            "mean": [m.mean(0).tolist(), m.mean(1).tolist(), m.mean()],
            "variance": [m.var(0).tolist(), m.var(1).tolist(), m.var()],
            "standard deviation": [m.std(0).tolist(), m.std(1).tolist(), m.std()],
            "max": [m.max(0).tolist(), m.max(1).tolist(), m.max()],
            "min": [m.min(0).tolist(), m.min(1).tolist(), m.min()],
            "sum": [m.sum(0).tolist(), m.sum(1).tolist(), m.sum()],
        }
        return r
    pprint(calculate([i for i in range(0, 9)]))


.. parsed-literal::

    {'max': [[6, 7, 8], [2, 5, 8], np.int64(8)],
     'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], np.float64(4.0)],
     'min': [[0, 1, 2], [0, 3, 6], np.int64(0)],
     'standard deviation': [[2.449489742783178,
                             2.449489742783178,
                             2.449489742783178],
                            [0.816496580927726,
                             0.816496580927726,
                             0.816496580927726],
                            np.float64(2.581988897471611)],
     'sum': [[9, 12, 15], [3, 12, 21], np.int64(36)],
     'variance': [[6.0, 6.0, 6.0],
                  [0.6666666666666666, 0.6666666666666666, 0.6666666666666666],
                  np.float64(6.666666666666667)]}
    

