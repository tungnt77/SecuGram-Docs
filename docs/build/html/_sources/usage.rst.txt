HOW-TO GUIDES
=====

Creating a website
------------
.. |png0| image:: img/00.png
.. |png1| image:: img/01.png
.. |png2| image:: img/02.png
.. |png3| image:: img/03.png
.. |png4| image:: img/04.png
.. |png5| image:: img/05.png
.. |png6| image:: img/06.png
.. |png7| image:: img/07.png
.. |png8| image:: img/08.png
.. |png9| image:: img/09.png

Go to https://server_ip:62443/SecuGram

1 - Create a virtual IP:
    In *Interfaces* menu, click **Add Virtual IP** button:
        
        |png0|

2 - Create a new app:
    In *Websites* menu, click **Add Website**

        |png1|

    After **Save**, click **Deploy**

        |png2|

3 - Configure the new app.
    *Websites disabled* menu, click over the application:
   
        |png3|

    On *WAF Protection* tab, enable waf rules:

        |png4|

    | Choose a virtual IP (previusly created on Interfaces menu). 
    | Configure ports (leave it blank if you dont need https port, same thing appy to http port). 
    | On **Real Application IP** box, fill real backend IP. Eg: "127.0.0.1:8080".
        
        |png5|
   
    Configure certificates if ssl ports are set.

        |png6|

    | Click *Expert Configuaration* tab => Nginx configuaration box: 
    | Comment line "proxy_pass $scheme://backend$separator$vhost$separator$plbsid$scheme;". 
    | Add line "proxy_pass 127.0.0.1:8080;" (enter the real backend application).

        |png7|

    Press the "play" button to enable the new app.
        
        |png9|

4 - Restart/Start Nginx
    In *Manage Nginx* Menu, choose action you need.

        |png8|
  
Status box explaination
------------

.. csv-table:: Status Box
   :file: status.csv




