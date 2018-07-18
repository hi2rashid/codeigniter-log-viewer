# codeigniter-log-viewer
Log Viewer for Codeigniter Application generated logs. Supports CI v3.1.9


Inspired by https://github.com/SeunMatt/codeigniter-log-viewer

Change Log:

Release version: v1.0.0
Date: 18-July-2018
* You can change the log viewer path by passing path as constructor.


# How to Use it

Copy following line of code to any of your Codeigniter Controller

## Method 1 ()
In `Welcome.php` Controller

    public function index() {
        $CILogs = new \CILogViewer\CILogViewer("/var/log/localhost/");
        echo $CILogs->showLogs();
        return;
    }
    
    
## Method 2 ()

In `Welcome.php` Controller

    public function index() {
        $CILogs = new \CILogViewer\CILogViewer($this->config->item('ci_log_path'));
        echo $CILogs->showLogs();
        return;
    }
    
In `application/config/config.php` Config file

    $config['ci_log_path'] = "/var/log/localhost/ci_log_path"
    
    
Also you need to make sure the directories `/var/log/localhost/ci_log_path` created and writable

In Terminal : `sudo mkdir -p /var/log/localhost/ci_log_path`
`sudo chmod -Rf 777 /var/log/localhost/ci_log_path`   (Make sure not to use 777 on production systems)
