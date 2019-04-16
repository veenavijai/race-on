# Stinger

Repository of Self Driving RC Car Stinger

Video:

<iframe width="560" height="315" 
    src="https://www.youtube.com/embed/ZWatCIyyhi4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>

Preliminary steps to begin with

1. SSH into the Pi<br/>
<code>ssh pi@raspberrypi.local</code>

2. Enter the virtual environment<br/>
<code>source /raceon/bin/activate</code>

3. Run the Initialization Script<br/>
<code>bash init_script.sh</code>

4. Check if the motors are enabled and working<br/>
<code>python start.py</code>

5. Stop the running motors<br/>
<code>python stop.py</code>

6. Run the car<br/>
<code>python run.py</code>
