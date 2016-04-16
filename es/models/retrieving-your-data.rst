Recuperando sus datos
####################

Como se dijo anteriormente, una de las funciones de la capa del Modelo es obtener datos desde múltiples tipos de almacenamiento.
La clase CakePHP modelo viene con algunas funciones que le ayudarán a buscar esta información, ordenarla, paginarla y filtrarla. La función más común que va a utilizar en los modelos es :php:meth:``Model::find()``

.. _model-find:

.. _model-find:

find
====

``find(string $type = 'first', array $params = array())``

Find es el caballo de batalla de múltiples funciones de todo lo que se refiere a la recuperación de datos.
``$type`` puede ser ``'all'``, ``'first'``, ``'count'``, ``'list'``,
``'neighbors'`` o ``'threaded'``, o cualquier buscador personalizado que quieras definir.
Manten en mente que el ``$type`` es sensible a mayuculas/minusculas. Si utilizas una letra mayuscula
(por ejemplo, ``All``) no producira el los resultados esperados.

``$params`` es utilizado para enviar todos los parametros de distintos tipos al metodo find(),
y tiene, por defecto, los siguientes parametros, los cuales son opcionales::


    array(
        'conditions' => array('Model.field' => $thisValue), //el arreglo de condiciones
        'recursive' => 1, //int
        //arreglo con los nombres de los campos
        'fields' => array('Model.field1', 'DISTINCT Model.field2'),
        //string or arreglo para definir el orden
        'order' => array('Model.created', 'Model.field3 DESC'),
        'group' => array('Model.field'), //campos para el GROUP BY
        'limit' => n, //int
        'page' => n, //int
        'offset' => n, //int
        'callbacks' => true //otros valores posibles son false, 'before', 'after'
    )

Tambien es posible agregar otros parametros. Algunos tipos de find() y algunos 
comportamientos hacen uso de esta habilidad, y tus propios modelos tambien pueden.

Si tu operacion con el find() falla en encontrar resultados, devolvera un arreglo vacio.

.. _model-find-first:

.. note::
    La documentación no se encuentra totalemente actualizada con el idioma español.

    Por favor, siéntase libre de enviarnos un pull request en
    `Github <https://github.com/cakephp/docs>`_ o utilizar el botón **Improve this Doc** para proponer directamente los cambios.

    Usted puede hacer referencia a la versión en Inglés en el menú de selección superior
    para obtener información sobre el tema de esta página.

.. _model-query:

:php:meth:`Model::query()`
==========================

.. meta::
    :title lang=es: Retrieving Your Data
    :keywords lang=es: upper case character,array model,order array,controller code,retrieval functions,model layer,model methods,model class,model data,data retrieval,field names,workhorse,desc,neighbors,parameters,storage,models
