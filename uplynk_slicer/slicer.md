Uplynk Slicer
=============

The Uplynk slicer is a tool that is used to consume video media and import the information into the Uplynk system.  This allows viewers to consume the media via the Uplynk architecture.  

Download
========

1. Create an Uplynk CMS user: https://cms.uplynk.com

2. Download the Linux slicer

        wget http://storage.uplynk.com/software/uplynk_slicer_linux_64-17061500-master.tbz2

5. Extract the tarball 

        tar -xjvf <slicer_tarball>.tbz2

6. Rename the extracted directory to `example_slicer` (for simplicity).
 
        mv <extracted_slicer_directory>/ example_slicer

7. Note a few of the files and a directory.

        drwxrwxr-x 2 rico rico     4096 Jun 15 14:01 plugins/
        -rwxrwxr-x 1 rico rico  2126927 Jun 15 14:01 liveslicer*
        -rwxrwxr-x 1 rico rico  1817838 Jun 15 14:01 slicer*

8. You can view the help menu for each with `-h`

        ➜  example_slicer git:(master) ✗ ./slicer -h

9. Add a channel in the CMS with `Slicer ID: <your_name>_live_slicer`.  You can choose any value you want for the `Channel Name`.

10. Open the `example.conf` file and update it to include your info.

11. Run the `liveslicer` and point it to your config file.

        ➜  example_slicer git:(master) ✗ ./liveslicer -config /path/to/your/config/file.config

