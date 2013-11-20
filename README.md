Unique Id Generator===================C# implementation of Twitter's Snowflake. A Generator can create sequentially unique IDs with a length of 8 bytes.  The ID consists of a timestamp (milliseconds since specific start date), a generator id and a sequence.This is the default configuration:- 41 bits for timestamp in milliseconds (can vary from 40 to 45)- 10 bits for generator id (can vary from 0 to 10)- 13 bits for sequence (can vary from 12 to 20)You can change this default values to gain more performance on a single process (more sequence-bits) or more performance in a cluster (more generator-bits).  With the default configuration you can create 1024 different generators. Each generator can create up to 8192 unique IDs per millisecond for 69 years.Performance measurement-----------------------Environment:- Intel Core i7-3740QM (2.7GHz)- 8GB RAM- Microsoft Windows 8.0 x64- Default configuration (41/10/13)### Single generatorDuration to generate 10'000'000 ids: 1'847 ms  Number of ids generated in 1 ms: 5'414  Number of ids generated in 1 s: 5'414'185### 8 generatorsDuration to generate 8'000'000 ids: 802 ms  Number of ids generated in 1 ms: 9'975  Number of ids generated in 1 s: 9'975'062### 64 generatorsDuration to generate 12'800'000 ids: 1'510 ms  Number of ids generated in 1 ms: 8'476  Number of ids generated in 1 s: 8'476'821