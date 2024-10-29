```python
import zlib
import struct

def read_png_chunks(file_path):
    with open(file_path, 'rb') as f:
        # Skip the PNG file signature (8 bytes)
        f.read(8)
        
        chunks = []
        while True:
            # Read the length of the chunk (4 bytes)
            length_data = f.read(4)
            if len(length_data) == 0:
                break
            length = struct.unpack('>I', length_data)[0]
            
            # Read the chunk type (4 bytes)
            chunk_type = f.read(4).decode('ascii')
            
            # Read the chunk data
            chunk_data = f.read(length)
            
            # Read the CRC (4 bytes)
            crc = f.read(4)
            
            chunks.append((chunk_type, chunk_data))
        
        return chunks

def decompress_last_idat(file_path):
    chunks = read_png_chunks(file_path)
    idat_chunks = [chunk_data for chunk_type, chunk_data in chunks if chunk_type == 'IDAT']
    
    if not idat_chunks:
        raise ValueError("No IDAT chunks found in the PNG file.")
    
    last_idat_data = idat_chunks[-1]
    decompressed_data = zlib.decompress(last_idat_data)
    
    return decompressed_data

if __name__ == "__main__":
    file_path = 'sctf.png'
    decompressed_data = decompress_last_idat(file_path)
    print(decompressed_data)
```