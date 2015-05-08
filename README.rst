=======================
JMessage Python Client
=======================

JMessage's officially supported Python client library for accessing JPush APIs. 

------------
Dependencies
------------
You need to install pycurl, to use jmessage python client, and nose for test.

.. code-block:: sh

    $ sudo pip install -r requirements.txt

------------
Installation
------------
To install jpush-api-python-client, simply:

.. code-block:: sh

    $ sudo pip install jmessage

or alternatively install via easy_install:

.. code-block:: sh

    $ sudo easy_install jmessage


or from source:

.. code-block:: sh

    $ sudo python setup.py install

-------
Testing
-------
For running the tests, you need the standard `unittest` module, shipped
with Python. 

To run JMessage tests, simply:

.. code-block:: sh

    $ nosetests -v

--------
Examples
--------
    You can see more examples in `examples <https://github.com/jpush/jpush-api-python-client/blob/master/examples>`_


JMessage Users Management
-----------------
    >>> from jmessage import JMessageSDK
    >>> import conf
    >>> sdk = JMessageSDK(conf.APPKEY, conf.MASTERSECRET)
    >>> sdk.users.register_users('user', [{'username': 'example', 'password': 123456}])
    [{u'username': u'example'}]
    >>> sdk.users.del_user('example')
    True


JMessage Groups Management
-----------------
    >>> from jmessage import JMessageSDK
    >>> import conf
    >>> sdk = JMessageSDK(conf.APPKEY, conf.MASTERSECRET)
    >>> sdk.groups.create_group(
    ...     'example_group_owner@py',
    ...     'PyCon', 
    ...     members_username=['example_user_01@py', 'example_user_02@py'],
    ...     group_desc="Conf for Pythonista!")
    {
        u'gid': 10003868,
        u'members_username': [u'example_user_01@py', u'example_user_02@py'],
        u'group_desc': u'Conf for Pythonista!',
        u'owner_username': u'example_group_owner@py',
        u'group_name': u'PyCon'
    }
    >>> sdk.groups.del_group(10003868)
    True


--------
Questions
--------
The best place to ask questions is our Q&A site:
http://www.jpush.cn/qa/
