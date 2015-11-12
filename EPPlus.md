# EPPlus
//Write to excel
 private ExcelPackage CreateexcelPackage()
        {
            //Get selected file
            HttpPostedFile file = Request.Files[0];
            MemoryStream mem = new MemoryStream();
            mem.SetLength((int)file.ContentLength);
            file.InputStream.Read(mem.GetBuffer(), 0, (int)file.ContentLength);
            //Create ExcelPackage
            var datafile = new ExcelPackage(mem);
            return datafile;
        }
