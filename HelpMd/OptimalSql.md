
### ��������ʹ��LinQ��ѯ�Ĺ����У��Ƽ������ʹ�õĲ�ѯ��ʽ��

	һ����ѯ���ͣ�
		1����������Id��ѯ��
			var bookSet = DbContext.Set<Book>().Find(bookId);
		2�����ݷ�������ѯ��
			var model = DbContext.Set<Book>().ToList().Single(s => s.Id == Int32.Parse(id));
			var model = DbContext.Set<Book>().Where(s => s.Id == id).Select(s => new Book { Name = s.Name, Price = s.Price });
		
		3����ѯ��ҳ��
			var queryable = DbContext.Set<Book>().Skip((pageIndex - 1) * pageSize).Take(pageSize).OrderBy(s => s.Id);
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
                totalCount = queryable.Count();
		4���������ѯ���⣺
			1���Ȳ�����������Ϣ��ѯ����֮���ٸ���������Ϣȥ�������ѯ��Ȼ����ϳ�һ���Լ���Ҫ�����ݼ���
		

	����ɾ�����ͣ�
		var model = DbContext.Set<Book>().Where(s => s.Id == id).delete();
		
	�����������ͣ�
		int result = db.Book.Where(s => s.Id == id).Update(s => new Book { Name = name });
 

