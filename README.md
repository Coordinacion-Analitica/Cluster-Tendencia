# Cluster-Tendencia
En el proyecto de maximización de venta en Alquería, se vio la necesidad de encontrar herramientas que permitieran agrupar clientes por comportamientos de compra. Esto quiere decir, agrupar clientes por tener tendencias de venta a la caída, otros a la subida y otros que se mantuvieran estables a través del tiempo. Esta agrupación nos podría dar información relevante al momento de ser cruzada con la segmentación comercial (Ver [Explicación Segmentos.gslides](https://docs.google.com/open?id=1Ag1OWkbl_uStretSSC7MXx2uyjCJTbtr0tCWyTbnN_E&authuser=ejlopezm%40alqueria.com.co&usp=drive_fs)) ya que se podría evidenciar comportamientos a través del tiempo de segmentos clave. Finalmente, la agrupación juega un papel relevante al momento de ser enlazada con los pronósticos de venta, ya que se evidencia comportamientos específicos de clientes dada su tendencia, mostrando así una estrategia viable para la toma de decisiones.

## Análisis & Software
En el archivo [Final Cluster.ipynb](https://github.com/Coordinacion-Analitica/Cluster-Tendencia/blob/main/Final%20Cluster.ipynb) se encuentra los códigos en **Python** que se utilizaron en la clusterización de tendencias de ventas de los clientes de Bogotá.
La clusterización se realizó mediante el *método de agrupación jerárquica dada una matriz de enlace*. Se utilizó la función **fcluster** del paquete **scipy.cluster.hierarchy**, para más información pueden remitirse a las siguientes páginas donde se especifica las características de las funciones:

* https://docs.scipy.org/doc/scipy/reference/cluster.hierarchy.html
* https://docs.scipy.org/doc/scipy/reference/generated/scipy.cluster.hierarchy.fcluster.html

## Tener en cuenta
Es importante tener en cuenta lo siguiente al momento de ejecutar el algoritmo:
* El insumo principal es **alq-analitica-dev.EXT.DIST_1-GRAL-SKU** en BigQuery.
* El esquema de **la clusterización está por tipología** ya que los comportamientos de venta de cada uno de los clientes depende de este. 
* El **método utilizado es supervisado**, lo cual significa que la interpretabilidad del cluster debe ser dada por el usuario.  
* El algoritmo genera una tabla de cliente-cluster que es enviada a **alq-analitica-dev.INPUT.DF_CLUSTER_DIST_1** en BigQuery.
