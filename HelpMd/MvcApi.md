
### �����й�MvcApi������Ŀ�Ľ��ܣ�ʹ����Ҫע�����¼��㣺
	
  * 1 MvcApi��Ŀ��ͨ��NuGet�����������Cicada�����ڽ��������һ��"Cicada.Boot.Aspnet.MVC",��װ��MVC��Ŀ����;
		ͬ����װһ��Cicada.Boot.Aspnet.WebApi�����ٰ�װһ��Cicada.Data.EntityFramework;Ȼ��MvcApi��Ŀ�漰����ܵĶ�������������ϡ�
  * 2 ��MvcApi��Ŀ���ҵ�Cicada.properties�ļ����򿪱༭���ж�Ӧ�����Ӽ��ɣ�����������£�
     * 2.1 Cicada.DI.AutoRegisterByProductName��ӦService��������ַ�����ǰ��#��ȥ������#�ž���ע�͵���˼����
     * 2.2 Cicada.Data.ProviderĬ��֧��MySql�����ʹ��SqlServer���Ͱ�ǰ���ע��ȥ������Ӧ�����ָĳ�SqlServer��
     * 2.3 Cicada.Data.ConnectionString�������ʵ����������������ļ��ɡ�
  * 3 Server�㣬ͬ��ͨ��NuGet�����������Cicada��,������һ����Cicada.Data.EntityFramework��,������ռ��ɣ���������������£�
     * 3.1 �Ҽ����ͨ����Entity Framework���������ɶ�Ӧ��EF����ӳ�������ʵ��ģ�ͣ��ð�װEF Power Tool�Ͷ�Ӧ�����ݿ�������
     * 3.2 Ȼ�����ݵľ���ʵ�ֿ��Բο����صĳ���
