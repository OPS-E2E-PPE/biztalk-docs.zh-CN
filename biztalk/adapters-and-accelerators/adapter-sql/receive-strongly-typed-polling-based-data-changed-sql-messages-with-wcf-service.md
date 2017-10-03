---
title: "使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a56ed382f6fa9c106b091b62406feba2dffe704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a>使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收强类型的轮询消息。 你可以指定适配器执行轮询数据库轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回的结果集。 在方案中必须使用强类型轮询你想要接收的强类型化结果集。 有关如何的适配器支持强类型轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  
  
> [!IMPORTANT]
>  如果你想要在单个应用程序中具有多个轮询操作，你必须指定**InboundID**作为连接以使其唯一的 URI 的一部分的连接属性。 你指定的入站的 ID 添加到要使之唯一的操作命名空间。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收强类型数据的支持更改消息、 创建.NET 应用程序和生成的 WCF 服务协定**TypedPolling**操作。 请确保你指定生成 WCF 服务约定时以下：  
  
-   必须指定**InboundID**作为连接 URI 的一部分。  
  
-   必须指定轮询语句**PollingStatement**绑定属性。  
  
 此外，如果你想要指定其他轮询相关时生成代理类中，绑定属性指定**PolledDataAvailableStatement**作为：  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**必须返回具有包含正值的第一个单元格的结果集。 如果第一个单元格不包含是正数值，该适配器将不会执行轮询语句。  
  
 作为轮询语句的一部分，请执行以下操作：  
  
1.  从员工表中选择所有行。  
  
2.  执行存储的过程 (MOVE_EMP_DATA) 将从员工表到 EmployeeHistory 表的所有记录。  
  
3.  执行存储的过程 (ADD_EMP_DETAILS) 将一条新记录添加到员工表。 此过程使用雇员姓名、 名称以及薪金作为参数。  
  
 若要执行这些操作，必须指定以下项作为**PollingStatement**属性绑定生成的 WCF 服务协定和帮助程序类时：  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 执行轮询语句后，选择从 Employee 表的所有记录，并接收来自 SQL Server 的消息。 MOVE_EMP_DATA 存储过程执行适配器后，所有记录被都移动到 EmployeeHistory 表。 然后，执行 ADD_EMP_DETAILS 存储过程将一条新记录添加到员工表。 下一次轮询执行将只返回单个记录。 此循环会持续关闭服务主机。  
  
## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a>配置与 SQL 适配器绑定属性的类型化的轮询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 除**PollingStatement**绑定属性外，本部分中列出的所有其他绑定属性都需要运行.NET 应用程序时。 必须指定**PollingStatement**之后才生成 WCF 服务协定绑定属性**TypedPolling**操作。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定是否想要执行**轮询**， **TypedPolling**，或**通知**入站操作。 默认值是**轮询**。 若要接收强类型的轮询消息，请将此设置为**TypedPolling**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 SQL 语句必须返回的结果集行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行绑定属性。|  
|**PollingIntervalInSeconds**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器将等待的间隔中的剩余时间。|  
|**PollingStatement**|指定要轮询的 SQL Server 数据库表的 SQL 语句。 你可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 null。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。 你可以指定任意数量的以分号分隔的 SQL 语句。 **重要说明：**为**TypedPolling**，生成元数据之前，必须指定此绑定属性。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，进一步阅读。  
  
## <a name="configuring-strongly-typed-polling-in-the-wcf-service-model"></a>配置 WCF 服务模型中的强类型轮询  
 若要接收**轮询**操作使用 WCF 服务模型时，你必须：  
  
1.  为生成的 WCF 服务协定 （接口） **TypedPolling**从适配器公开的元数据的操作。 若要执行此操作，你无法使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 在生成 WCF 服务协定，对于此示例，请确保：  
  
    -   你指定**InboundID**作为**员工**。  
  
    -   指定轮询语句**PollingStatement**绑定属性。 对于此示例中，指定轮询语句作为:  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
2.  实现此接口从 WCF 服务。  
  
3.  托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例轮询员工表。 此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。 在示例提供了一个脚本以生成这些项目。 有关这些示例的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **TypedPolling_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF 服务协定和类  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**TypedPolling**操作。 有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示为生成的 WCF 服务协定 （接口） **TypedPolling**操作。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  
  
### <a name="the-message-contracts"></a>消息协定  
 消息协定命名空间将被修改， **InboundID**中连接 URI，如果指定参数。 在此示例中，指定形式的入站的 ID**员工**。 请求消息返回强类型化结果集。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  
  
    public TypedPolling() {  
    }  
  
    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF 服务类  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。 文件的名称是 SqlAdapterBindingService.cs。 你可以将插入的逻辑来处理**TypedPolling**直接插入此类操作。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : TypedPolling_Employee {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-strongly-typed-inbound-messages-for-polling-operation"></a>轮询操作接收强类型化入站的消息  
 此部分提供有关如何编写.NET 应用程序以接收使用强类型的入站的轮询消息说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a>从 SQL 适配器接收轮询消息  
  
1.  使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**TypedPolling**操作。 请确保你指定生成此示例中的 WCF 服务协定时以下：  
  
    -   必须指定**InboundID**作为**员工**。  
  
    -   必须指定轮询语句**PollingStatement**绑定属性。 对于此示例中，指定轮询语句作为:  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
     有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。 生成服务协定和帮助程序类时，可以选择指定的绑定属性。 这可确保它们正确设置生成的配置文件中。  
  
2.  实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。 **TypedPolling**此类的方法可以处理从接收的数据遇到错误时引发异常中止轮询事务， **TypedPolling**操作; 否则为方法不返回任何内容。 必须属性 WCF 服务类，如下所示：  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     在**TypedPolling**方法，你可以直接实现你的应用程序逻辑。 SqlAdapterBindingService.cs 中找不到此类。 此示例中的此代码子类**SqlAdapterBindingService**类。 在此代码中，接收作为强类型化结果集的轮询消息写入控制台。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据作为连接 URI 的一部分，则必须实现以下类用于传递的 SQL Server 数据库的凭据。 在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  创建**SqlAdapterBinding**和通过指定绑定属性中配置的轮询操作。 可以在代码中显式或配置中以声明方式执行此操作。 至少，你必须指定**InboundOperationType**， **PolledDataAvailableStatement**，和**PollingStatement**。  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.TypedPolling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  指定 SQL Server 数据库凭据，方法是实例化**PollingCredentials**在步骤 3 中创建的类。  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  创建在步骤 2 中创建的 WCF 服务的实例。  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。 数据库连接 URI 不能包含入站 id。 你还必须指定此处的凭据。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  将服务终结点添加到服务主机。 为此，请执行以下操作：  
  
    -   使用在步骤 4 中创建的绑定。  
  
    -   指定连接 URI，其中包含凭据，如果需要，一个入站的 id。  
  
    -   作为"TypedPolling_Employee"指定的协定。  
  
    ```  
    // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Empliyee");  
    serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
    ```  
  
9. 若要接收轮询数据，请打开服务主机。 每当查询返回一个结果集，该适配器将返回数据。  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. 若要终止轮询，关闭服务主机。  
  
    > [!IMPORTANT]
    >  适配器将继续轮询，直到关闭服务主机。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>示例  
 下面的示例演示执行员工表的轮询查询。 轮询语句将执行下列任务：  
  
1.  从员工表中选择的所有记录。  
  
2.  执行上述 MOVE_EMP_DATA 存储过程以从员工表的所有记录都移到 EmployeeHistory 表。  
  
3.  执行上述 ADD_EMP_DETAILS 存储过程以将单个记录添加到员工表。  
  
 第一条的轮询消息将包含从 Employee 表的所有记录。 后续的轮询消息将包含仅由 ADD_EMP_DETAILS 存储过程插入的最新记录。 适配器将继续轮询，直到按关闭服务主机`<RETURN>`。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)