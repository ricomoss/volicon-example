Uplynk Slicer
=============

The Uplynk slicer is a tool that is used to consume video media and import the information into the Uplynk system.  This allows viewers to consume the media via the Uplynk architecture.  

Download
========

1. Download the Linux slicer

        wget http://storage.uplynk.com/software/uplynk_slicer_linux_64-17061500-master.tbz2

2. Extract the tarball 

        tar -xjvf <slicer_tarball>.tbz2

3. Rename the extracted directory to `example_slicer` (for simplicity).
 
        mv <extracted_slicer_directory>/ example_slicer

4. Note a few of the files and a directory.

        drwxrwxr-x 2 rico rico     4096 Jun 15 14:01 plugins/
        -rwxrwxr-x 1 rico rico  2126927 Jun 15 14:01 liveslicer*
        -rwxrwxr-x 1 rico rico  1817838 Jun 15 14:01 slicer*

5. You can view the help menu for each with `-h`

        ➜  example_slicer git:(master) ✗ ./slicer -h

6. Add a channel in the CMS with `Slicer ID: <your_name>_live_slicer`.  You can choose any value you want for the `Channel Name`.

7. Open the `example.conf` file and update it to include your info.

8. Run the `liveslicer` and point it to your config file.

        ➜  example_slicer git:(master) ✗ ./liveslicer -config /path/to/your/config/file.config

Note: The `liveslicer` needs to run uninterrupted to function.  All API calls must be made from a different process.

9. The channel will begin streaming your content.  Open the URL for your channel, which can be found in `Editor -> Test Players` choose the "blue" link.
