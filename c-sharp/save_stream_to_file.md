## How to Save a Stream into a File

First establish a file stream from the destination file path. Then open the stream and copy it to the destination file stream.

```C#
// Write in the incoming file to the temporary file path
using (var fs = System.IO.File.Create(filePath))
using (Stream s = wgsReportFile.FileUpload.OpenReadStream()) {
	s.Seek(0, SeekOrigin.Begin);
	await s.CopyToAsync(fs).ConfigureAwait(false);
}
```

### References:

https://stackoverflow.com/questions/411592/how-do-i-save-a-stream-to-a-file-in-c
