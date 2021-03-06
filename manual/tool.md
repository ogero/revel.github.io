---
title: revel cmd
layout: manual
---

## Build and Run

- The `revel` command line tool is required to use the Revel framework
- The code/app is in a seperate repository [github.com/revel/cmd](https://github.com/revel/cmd)
- It is NOT included with the main framework
- To install, run the command below

{% highlight sh %}
	$ go get github.com/revel/cmd/revel
{% endhighlight  %}

<div class="alert alert-danger">Gotcha: The command is in the subdirectory '/revel' ie <code>revel/cmd/revel</code> and not <code>revel/cmd</code></div>	
	
Now run it:

	$ bin/revel
	~
	~ revel! http://revel.github.io
	~
	usage: revel command [arguments]

	The commands are:

		new         create a skeleton Revel application
		run         run a Revel application
		build       build a Revel application (e.g. for deployment)
		package     package a Revel application (e.g. for deployment)
		clean       clean a Revel application's temp files
		test        run all tests from the command-line

	Use "revel help [command]" for more information.



## Quick Ref

<div class="alert alert-info">These docs maybe be out of date with current command, expect sync soon</div>


 - Please refer to the tool's built-in help functionality for the latest information on the individual commands.
 
<div class="alert alert-success">If not specified, the <a href="appconf.html#runmodes"><code>run_mode</code></a> on all commands defaults to <b>dev</b></div>


<a name="new"></a>

#### `revel new [import_path] [skeleton]`

Creates a few files to get a new Revel application running quickly.

- Copies files from the [`revel/skeleton`](https://github.com/revel/revel/tree/master/skeleton) directory
- Skeleton is an optional argument, provided as an alternate skeleton path
{% highlight sh %}
    revel new bitbucket.org/mycorp/my-app
{% endhighlight %}
<a name="run"></a>
    
#### `revel run [import_path] [run_mode] [port]`
{% highlight sh %}
	// run in dev mode
	revel run bitbucket.org/mycorp/my-app

	// run in prod mode on port 9999
    revel run bitbucket.org/mycorp/my-app prod 9999
{% endhighlight %}   
<a name="build"></a>

#### `revel build [import_path] [target_path]`

- Build the Revel web application named by the given import path. 
- This allows it to be deployed and run on a machine that lacks a Go installation.

{% highlight sh %}
    revel build github.org/mememe/mega-app /path/to/deploy/mega-app
{% endhighlight %}   

<div class="alert alert-danger">WARNING: The target path will be completely deleted, if it already exists!</div>

<a name="package"></a>

#### `revel package [import_path] [run_mode]`

- Build the Revel web application named by the given import path. 
- This allows it to be deployed and run on a machine that lacks a Go installation.

{% highlight sh %}
    revel package github.com/revel/revel/samples/chat
    > Your archive is ready: chat.tar.gz
{% endhighlight %}
  
<div class="alert alert-danger">WARNING: The target path will be completely deleted, if it already exists!</div>

<a name="clean"></a>
    
#### `revel clean [import_path]`

- Clean the Revel web application named by the given import path
- Deletes the `app/tmp` directory.
{% highlight sh %}
    revel clean github.com/revel/samples/booking 
{% endhighlight %}

<a name="test"></a>
    
#### `revel test [import_path] [run_mode] [suite.method]`

- Run all tests for the Revel app named by the given import path.
{% highlight sh %}
    revel test github.com/revel/samples/booking dev
{% endhighlight %}

    