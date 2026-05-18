# Insecure Deserialization

Insecure deserialization occurs when an application deserializes untrusted data without proper validation, potentially allowing attackers to manipulate objects and execute arbitrary code.

## Affected Technologies

- Java (ObjectInputStream)
- PHP (unserialize)
- Python (pickle)
- .NET (BinaryFormatter)

## Prevention

- Never deserialize untrusted data
- Use simple data formats (JSON) instead of object serialization
- Implement integrity checks (digital signatures) on serialized data
- Use type-safe deserialization
- Run deserialization in a sandbox
