# UUID (a.k.a GUID) in Java 
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-uuid)  
**Purpose**: Represents 128-bit long value that is unique for all practical purposes. Can be used to assign id to elements of some set (set in mathematical sense) used among different systems.
## Structure
* A UUID is made of up of hex digits  (4 chars each) along with 4 “-” symbols which make its length equal to 36 characters.
* The Nil UUID is a special form of UUID in which all bits are set to zero.
* 123e4567-e89b-42d3-a456-556642440000
* xxxxxxxx-xxxx-Bxxx-Axxx-xxxxxxxxxxxx
* A - A represents the variant which determines the layout of the UUID. All other bits in the UUID depends on the setting of the bits in the variant field. The variant is determined by 3 most significant bit of A.
* B - represents version of GUID
## Versions
* The only difference between UUIDv3 and UUIDv5 is the Hashing Algorithm – v3 uses MD5 (128 bits) while v5 uses SHA-1 (160 bits).
* The UUID v4 implementation uses random numbers as the source. The Java implementation is SecureRandom – which uses an unpredictable value as the seed to generate random numbers to reduce the chance of collisions.