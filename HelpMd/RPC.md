
### �����й�RPC������Ŀ�Ľ��ܣ����а���RPC����Server����RPC�ͻ��ˣ�Client����
	һ��RPC����˵Ľ��ܣ�
		* 1.1��RPC�������Ŀ������һ�㴦�����ͨ��NuGet���������صĳ������Cicada.Boot��Cicada.Rpc����Ϊ�õ���һ�㴦�����
			���Ҫ�����ϵͳ��������Ҳ����Cicada.Boot.Service��
		* 1.2�����һ�������������ҵ����ļ��У���������ΪServices��������������Ƿ����Ҫʵ�ֵĹ����ļ�������Ҫ���ɵĶ���ӿں�
			Ҫʵ�ֵĶ���ӿڹ��ܣ������ɽӿڷ�������˳��a.�ҵ���Ŀ����·����\packages\Cicada.Rpc.1.0.0.5\tools�����򿪱༭demo.thrift
			�������涨����Ƿ���˶��⿪�ŵ����ݽӿڣ�������ɺ󱣴棻b.˫��ִ������c#����.bat�ļ���c.Ȼ��Ϳ��԰�gen-csharp�ļ����
			���ݿ������ղŴ�����Service�ļ��
		* 1.3����Service�ļ��ﴴ��һ���̳���Thrift***.Iface,Ȼ����������ɵĽӿڽ���ʵ�֡�
		* 1.4�����Ҫ���õľ���Cicada.properties����������AutoRegisterByProductName����ΪҪ�����ϵͳ����Windows Service��Ҫ����
			��Ӧ����Ϣ��Ȼ�����RPC��������������ã��������������ο�����˵����
	
	
	����RPC�ͻ��˵Ľ��ܣ�
		* 2.1��RPC�Ŀͻ���ʾ���õ�Ҳ��һ�㴦�����Ҫ���õĳ��������Cicada.Boot��Cicada.Rpc��
		* 2.2��ͬ������Service�ļ��У�������õ���Ȼ�����ɵĽӿ��ļ���
		* 2.3������������Cicada.properties�����Ȼ���AutoRegisterByProductName��Ȼ�����RPC�ͻ������������Ϣ����������˵��
			��д��Ӧ��Ϣ��
		
		
	����RPC����ӿ�ģ��ʾ����
			struct Customer {   #  ����ͻ���
				1: i32 customerId   #�ͻ�����
				2: string name		#�ͻ�����
				3: Address addressInfo	#��ַ��Ϣ
			}

			struct	Address{	#��ַ��
				1: string city	#����
				2: string street	#�ֵ�
			}
			  
			service ThriftCustomerService {  #  �������ӿ�
				i32 Add(1:Customer customer)	#���һ���ͻ��������¿ͻ�����
				Customer Get(1:i32 id)			#���ݿͻ������ȡָ���ͻ���Ϣ
				list<Customer> GetList()		#��ȡ���пͻ�	
				map<i32, Customer> GetMap()		#��ȡ���пͻ�	
			} 
		