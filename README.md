# Twitter-sentimental-analysis-on-GST
The project is about finding the sentiments of the people on the topic of GST on twitter by sentimental analysis of the twitter data onto the topic Using hadoop eco system and excel

## Getting Started

### Prerequisites
the project needs to be run on the a hadoop framework needs to install the following:
1. Apache hadoop
2. Apache hive - for processing the data
3. Apache flume - for streaming the data from twitter server
4. Excel

Installing guide:
```https://data-flair.training/blogs/hadoop-ecosystem-components/```

## Running the Project
The number of steps have to be performed :
### Streaming of the data

We will be using flume for the streaming of the data from the twitter server 
#### Setting up the Flume
Copy ```flume-sources-1.0-SNAPSHOT.jar``` to ```/usr/lib/flume-ng/plugins.d/twitter-streaming/lib/flume-sources-1.0-SNAPSHOT.jar```
```Copy twitter.conf file provided to $FLUME_HOME/conf directory.
   
   Edit the twitter.conf file and set parameters in accordance with the Twitter Agent.
   
   Fill the correct Twitter's developer account authentication details.
   
   If you wish to edit the keywords and add Twitter API related data, do it. 
   
   Now, save the changes done in the file.
   ```

#### Starting Flume agent

    $ hadoop fs -mkdir <destination>
    $ $FLUME_HOME/bin/flume-ng agent --conf $FLUME_HOME/conf/ -f $FLUME_HOME/conf/twitter.conf  Dflume.root.logger=DEBUG,console -n TwitterAgent

### Processing data

Once the data is been taken into the HDFS now it hould be processes ussing the Hive
```first the data is loaded from raw jason format to hive table using the serdes

  now place the proc_hive.hql file and APPIN dictionary file in the same folder and run the proc_hive   
  
  It will output a file that is to be copied into a result.csv file and the imported into an excel file
```

### Visualizing our Output

![alt text](https://github.com/mayankjn34/Twitter-sentimental-analysis-on-GST/blob/master/Project.JPG "Analysis")


## Acknowledgments


https://acadgild.com/blog/sentiment-analysis-on-tweets-with-apache-hive-using-afinn-dictionary
