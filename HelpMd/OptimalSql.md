
### ��������ʹ��LinQ��ѯ�Ĺ����У��Ƽ������ʹ�õĲ�ѯ��ʽ��

 * һ����ѯ���ͣ�  
    1����������Id��ѯ��  
        var bookSet = DbContext.Set<Book>().Find(bookId);  
	2�����ݷ�������ѯ��  
	    var model = DbContext.Set<Book>().Single(s => s.Id == Int32.Parse(id));
	    var model = DbContext.Set<Book>().Where(s => s.Id == id).Select(s => new Book { Name = s.Name, Price = s.Price });
		
	3����ѯ��ҳ��
	    var bookDataSet = DbContext.Set<Book>();
	    var queryable=  bookDataSet.Skip((pageIndex - 1) * pageSize).Take(pageSize).OrderBy(s => s.Id);
        if (id != 0)
        {
            queryable = queryable.Where(s => s.Id == id);
        }
        if (!string.IsNullOrEmpty(name))
        {
            queryable = queryable.Where(s => s.Name.Contains(name));
        }
        if (price != 0)
        {
            queryable = queryable.Where(s => s.Price == price);
        }
	    var list = bookDataSet.toList();
        var totalCount = bookDataSet.Count();
	4���������ѯ���⣺
	1���Ȳ�����������Ϣ��ѯ����֮���ٸ���������Ϣȥ�������ѯ��Ȼ����ϳ�һ���Լ���Ҫ�����ݼ���
		

 * ����ɾ�����ͣ�
	    var model = DbContext.Set<Book>().Where(s => s.Id == id).delete();
		
 *	�����������ͣ�
	    int result = db.Book.Where(s => s.Id == id).Update(s => new Book { Name = name });
		
 * �ġ����������
    	public bool AddTwoInfo()
            {
                var book = new Book { BookAuthor = "·ң", BookTitle = "ƽ��������", BookData = DateTime.Now };
                var userInfo = new UserInfo { UserCode = "luyao001", UserName = "·ң" };
                int result = 0;
                using (var transaction = new TransactionScope())
                {
                    //������һ������
                    DbContext.Set<Book>().Add(book);
                    //�����ڶ�������
                    DbContext.Set<UserInfo>().Add(userInfo);
    
                    result= DbContext.SaveChanges();
                    //�ύ����
                    transaction.Complete();
                }
                return result > 0 ? true : false;
            }
 * �塢EFʹ��ע��ĵ㣺
        1�����ݿ�����ֺ����ݱ�����ֲ����õ㣨.����ϣ���Ȼ�ᱨ��
        2��var model = DbContext.Set<Book>().Where(s => s.Id == AAA).update(...)���ʹ����ע�⣺
            a.����������������
            b.����������������String����
            c.���a��b���������������㣬ʹ��ʱ����AAA�͵ö��������棬��������쳣��
 

