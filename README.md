# Designing Data-Intensive Applications Notes



## Part I. Foundations of Data Applications

### 1. Reliable, Scalable, and Maintainable Applications

### 2. Data Models and Query Languages

### 3. Storage and Retrieval

### 4. Encoding and Evolution

**difference between Serialization and Marshalling**
This question has been asked before, on StackOverflow.[Here](https://stackoverflow.com/questions/770474/what-is-the-difference-between-serialization-and-marshaling)

Both do one thing in common - that is *serializing* an Object. Serialization is used to transfer objects or to store them.But:
- **Serialization**: When you serialize an object, only the member data within that object is written to the byte stream; not the code that actually implements the object.
- **Marshalling**: Term Marshalling is used when we talk about **passing Object to remote objects(RMI)**. In Marshalling Object is serialized(member data is serialized) + *Codebase* is attached.
***So Serialization is a part of Marshalling.***

*Codebase* is information that tells the receiver of Object where the implementation of this object can be found. Any program that thinks it might ever pass an object to another program that may not have seen it before must set the codebase, so that the receiver can know where to download the code from, if it doesn't have the code available locally. The receiver will, upon deserializing the object, fetch the codebase from it and load the code from that location.

