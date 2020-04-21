# DoppelGANger

## Method Overview

### Assumptions

Assume a dataset can be modeled as $\mathcal{D} = \{ O^1 , O^2, ..., O^n\}$ where $O^i$ is an object representing an atomic, high-dimensional data element, i.e., the combination of a single time series with its associated metadata. More precisely, each object $O^i = (A^i, R^i)$ contains $m$ *attributes* $A^i = [A_1^i, A_2^i, ..., A_m^i]$. For example, attribute $A_j^i$ could represent user $i$'s physical location. Note that this model can support datasets in which multiple objects have the same set of attributes. 

The second component of each object is a time series of *records* $R^i = [R_1^i, R_2^i, ..., R_{T^i}^i]$. For example, in retail, the time series may contain the numbers of products that user $i$ purchases on a given day. Different objects may contain different numbers of records (i.e., time series of different lengths). The number of records in object $O^i$ is given by $T^i$. Each record $R_j^i = (t_j^i, f_j^i)$ contains a *timestamp* $t_j^i$ and $K$ features $f_j^i = [f_{j, 1}^i, f_{j, 2}^i, ..., f_{j, 1K^i]$ (e.g., the number of each product among all $K$ products that the user purchases). 