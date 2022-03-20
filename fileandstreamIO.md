# File and Stream I/O

transfer of data from or to a storage, in System.IO namespaces we can read and write, used to interact with files and directories.

used file and directory classes

1-File: provides static methods for creating, copying, deleting, moving, and opening files, and helps create a FileStream object.-1

2-FileInfo: provides instance methods for creating, copying, deleting, moving, and opening files, and helps create a FileStream object.

3-Directory: provides static methods for creating, moving, and enumerating through directories and subdirectories.

4-DirectoryInfo: provides instance methods for creating, moving, and enumerating through directories and subdirectories.

Path: provides methods and properties for processing directory strings in a cross-platform manner.
Streams is a sequence of bytes that you can use to read from and write.
Streams involve three fundamental operations:
Reading: transferring data from a stream into a data structure, such as an array of bytes.
Writing: transferring data to a stream from a data source.
Seeking: querying and modifying the current position within a stream.

commonly used stream classes

FileStream: for reading and writing to a file.

IsolatedStorageFileStream: for reading and writing to a file in isolated storage.

MemoryStream: for reading and writing to memory as the backing store.

BufferedStream: for improving performance of read and write operations.

NetworkStream: for reading and writing over network sockets.

PipeStream: for reading and writing over anonymous and named pipes.

CryptoStream: for linking data streams to cryptographic transformations.

we should handle exceptions in filesystem methods

Reading or writing a large amount of data we should perform these tasks asynchronously 

Compression refers to the process of reducing the size of a file for storage.
classes are frequently used in compressing and decompressing files and streams:

ZipArchive : for creating and retrieving entries in the zip archive.

ZipArchiveEntry : for representing a compressed file.

ZipFile : for creating, extracting, and opening a compressed package.

ZipFileExtensions : for creating and extracting entries in a compressed package.

DeflateStream : for compressing and decompressing streams using the Deflate algorithm.

GZipStream : for compressing and decompressing streams in gzip data format.

StreamWriter: Implements a TextWriter for writing characters to a stream in a particular encoding.

 
