Guzzle 6 Adapter
================

An HTTPlug adapter for the `Guzzle 6 HTTP client`_.

To install the Guzzle adapter, which will also install Guzzle itself (if it was
not yet included in your project), run:

.. code-block:: bash

    $ composer require php-http/guzzle6-adapter

Then begin by creating a Guzzle client, passing any configuration parameters you
like::

    use GuzzleHttp\Client as GuzzleClient;

    $config = [
        // Config params
    ];
    $guzzle = new GuzzleClientClient($config);

Then create the adapter::

    use Http\Adapter\Guzzle6\Client as GuzzleAdapter;

    $adapter = new GuzzleAdapter($guzzle);

And use it to send synchronous requests::

    use GuzzleHttp\Psr7\Request;

    $request = new Request('GET', 'http://httpbin.org');

    // Returns a Psr\Http\Message\ResponseInterface
    $response = $adapter->sendRequest($request);

Or send asynchronous ones::

    use GuzzleHttp\Psr7\Request;

    $request = new Request('GET', 'http://httpbin.org');

    // Returns a Http\Promise\Promise
    $promise = $adapter->sendAsyncRequest(request);

.. include:: includes/further-reading-async.inc

.. _Guzzle 6 HTTP client: http://docs.guzzlephp.org/
