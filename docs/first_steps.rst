=============
First Steps
=============

Welcome to the UNIFR API e-puck's documentation. 

unifr_api_epuck is a simple API wrapper that lets you control a real or simulated e-puck robot. 
Please find below the instructions to get started with the API for Python3.

Submitted by: David Roman Frischer

Object detection section by: Vincent Carrel

Supervisor: Dr. Julien Nembrini

github : https://github.com/davidfrisch/UNIFR_API_EPUCK

Requirements
--------------

*  Python3.x on your computer.
*  Webots or a real e-puck.


How To Start
---------------

With Real Robots
====================

1. How to install the package from your terminal.

    .. code-block:: shell

        $ pip install unifr_api_epuck


2. How to implement
    * To import the package:
    
    .. code-block:: python

        from unifr_api_epuck import wrapper
    
    * To create an instance of the robot:

    .. code-block:: python
    
        #Put the IP address of your robot.
        MY_IP = '192.168.43.125' 
        r = wrapper.get_robot(MY_IP)

    * To control the robot by calling its actions:

    .. code-block:: python

        r.init_sensors() #initiates the sensors
        r.set_speed(-2, 2) #makes it turn around itself

        #infinite loop
        while r.go_on():
            prox_values = r.get_prox() #gets the values of the proximity sensors
            print(prox_values)

        r.clean_up() #makes a reset

3. To run the file
        
        .. code-block:: shell

            $ python3 my_controller_file.py 


With Webots
==============

1. How to install the package from your terminal.
    .. code-block:: shell

        $ pip install unifr_api_epuck


2. How to implement your Python controller
    * To import the wrapper from the package:
    
    .. code-block:: python

        from unifr_api_epuck import wrapper
    
    * To create an instance of the robot:

    .. code-block:: python
    
        r = wrapper.get_robot()

    * To control the robot by calling its actions:

    .. code-block:: python

        r.init_sensors() #initiates the sensors
        r.set_speed(-2, 2) #makes it turn around itself

        #infinite loop
        while r.go_on():
            prox_values = r.get_prox() #gets the values of the proximity sensors
            print(prox_values)

        r.clean_up() #makes a reset


3. To run the file:
    
    * ⏯  press play on Webots


Simple Example Code
--------------------

| Q: What does it do ?
| A: The robot goes forward at a speed of 2 and prints its proximitiy sensor values.

.. code-block:: python

    from unifr_api_epuck import wrapper
    
    ip_addr = '192.168.43.125'
    r = wrapper.get_robot(ip_addr)
    
    r.set_speed(2)        #sets the speed of the wheels
    r.init_sensors()      #initiates the proximity sensor

    #infinite loop
    while r.go_on():
        print(r.get_prox()) #prints the proximity sensor values on the terminal

        #inserts some more code here to control your robot

    r.clean_up()



Graphic User Interface 
--------------------------
    * A GUI is available in the package. To start it, please run the following command:
        
    .. code-block:: shell

        $ python3 -m unifr_api_epuck -g



Sources
---------

Wifi Protocol between Robot <--> computer
    https://www.gctronic.com/doc/index.php?title=e-puck2_PC_side_development#WiFi_2

    http://projects.gctronic.com/epuck2/complete.py
    
    https://github.com/nembrinj/epuckAPI/tree/master

Webots 
    https://www.cyberbotics.com/doc/reference/nodes-and-api-functions

Multiprocess
    https://docs.python.org/3/library/multiprocessing.html#multiprocessing.managers.SyncManager  

    https://stackoverflow.com/questions/2545961/how-to-synchronize-a-python-dict-with-multiprocessing

Socket errors
    https://docs.python.org/3/library/exceptions.html#OSError

Pi-Puck
    https://pi-puck.readthedocs.io/en/latest/
    
    https://github.com/yorkrobotlab/pi-puck
    
    https://github.com/gctronic/Pi-puck
        

.. image:: res/unifr_logo.png
    :width: 100
    :alt: UNIFR logo



.. image:: res/humanist_logo.jpg
    :width: 100
    :alt: Human-IST logo

