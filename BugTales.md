## circular buffer-based debugging

Basically the technique is to create a data structure that encompasses or describes the problem you are trying to debug, packing that structure into an appropriately-sized (meaning small!) circular buffer, instantiating the buffer somewhere readily available for post-crash processing, and updating it at appropriate times in the code. After the crash happens you open up the core file and examine the contents of the buffers. Depending on what you are trying to do you may need multiple buffers going at once, for example for both a message producer and consumer. The advantages to this technique are:

It requires minimal interaction with the existing code to generate useful information.
It's leaner compute-wise than printf-style debugging and data won't be dropped.
It enriches the ability to troubleshoot offline via debugger.
The cost is mainly the memory required to instantiate the buffer(s) and obviously the buffer and structure sizes chosen should be the minimum required to elicit useful information.
