---
title: 从使用 WCF 服务模型的 SQL 接收查询通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5cff3344128e1471b57b387aaa8597c22a11d85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368324"
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a>从使用 WCF 服务模型的 SQL 接收查询通知
本主题演示如何配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 数据库接收查询通知消息。 为了演示通知，请考虑表中的，员工，"状态"列。 一条新记录插入到此表时，状态列的值设置为 0。 你可以配置适配器以通过使用用于检索作为"0。 具有状态列的所有记录的 SQL 语句注册通知接收通知 您可以通过指定的 SQL 语句来实现**NotificationStatement**属性绑定。 适配器客户端收到通知后，它可以包含用于执行 SQL Server 数据库上的所有后续任务的逻辑。 在此示例中，为简单起见，适配器客户端列出所有记录表中的将状态列设为"0。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图的用户定义类型使用 SQL 适配器操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)主题之前开始开发应用程序.  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>使用 SQL 适配器的绑定属性中配置通知  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置 SQL Server 从接收通知的属性。 必须运行.NET 应用程序以从 SQL Server 数据库中接收通知时指定这些绑定属性。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationStatement**|指定的 SQL 语句 (SELECT 或 EXEC \<*存储过程*\>) 用于对查询通知注册。 仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取通知消息。|  
|**NotifyOnListenerStart**|指定适配器是否启动侦听器时在向适配器客户端发送了通知。|  
  
 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要从 SQL Server 中接收通知，请阅读更多。  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>配置通知使用 WCF 服务模型  
 若要接收的通知使用 WCF 服务模型，您必须：  
  
1. 为生成的 WCF 服务协定 （接口）**通知**从由适配器公开的元数据的操作。 若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
2. 生成的 WCF 客户端**选择**Employee 表上的操作。 若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
3. 实现此接口中的 WCF 服务。  
  
4. 托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例接收为 Employee 表的通知。 这些示例提供了一个脚本来生成表。 有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **Notification_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF 服务约定和类  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**通知**操作。 有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示 WCF 服务协定 （接口） 为生成**通知**操作。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>消息协定  
 下面是通知操作的消息约定。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF 服务类  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。 文件的名称是 SqlAdapterBindingService.cs。 您可以将逻辑来处理**通知**直接在此类操作。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a>使用 WCF 服务模型的接收查询通知  
 本部分说明了如何编写.NET 应用程序以接收查询通知使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
#### <a name="to-receive-query-notifications"></a>若要接收查询通知  
  
1. 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 客户端**选择**上的操作**员工**表。 将使用此客户端收到通知消息后执行的 Select 操作。 添加新类，TableOperation.cs 到你的项目并添加下面的代码段，以执行选择操作。  
  
   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Linq;  
   using System.Text;  
  
   namespace Notification_ServiceModel  
   {  
       public class TableOperation  
       {  
           public void TableOp()  
           {  
               ///////////////////////////////////////////////////////////////////////  
               // CREATING THE CLIENT  
               ///////////////////////////////////////////////////////////////////////  
  
               TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
               client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
               client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
               ///////////////////////////////////////////////////////////////////////  
               // OPENING THE CLIENT  
               ///////////////////////////////////////////////////////////////////////  
  
               try  
               {  
                   Console.WriteLine("Opening Client...");  
                   client.Open();  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               ///////////////////////////////////////////////////////////////////////  
               // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
               ///////////////////////////////////////////////////////////////////////  
               schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
               try  
               {  
                   selectRecords = client.Select("*", "where Status=0");  
               }  
  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               Console.WriteLine("The details of the newly added employee are:");  
               Console.WriteLine("********************************************");  
               for (int i = 0; i < selectRecords.Length; i++)  
               {  
                   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                   Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                   Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                   Console.WriteLine();  
               }  
               Console.WriteLine("********************************************");  
  
   ```  
  
   > [!IMPORTANT]
   >  由于此代码片段执行 Employee 表包含 Point UDT 列上的操作，因此请确保将 UDT DLL 放在项目的 \bin\Debug 文件夹下运行应用程序时。  
  
2. 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**通知**操作。  
  
    有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。 在生成服务协定和帮助程序类时，可以选择指定的绑定属性。 这可确保它们正确设置生成的配置文件中。  
  
3. 实现在步骤 2 中生成的接口和帮助程序类中的 WCF 服务。 **通知**此类方法可以引发异常来中止操作，如果遇到错误，处理从接收的数据**通知**操作; 否则该方法执行不返回任何内容。 必须按如下所示属性的 WCF 服务类：  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    内**通知**方法，可以直接实现应用程序逻辑。 可以 SqlAdapterBindingService.cs 中找到此类。 此代码在此示例中的嵌套类**SqlAdapterBindingService**类。 在此代码中，收到的通知消息写入控制台。 此外， **TableOp**方法内的**TableOperation**类调用以执行选择操作。  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
   public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
   {  
       public override void Notification(Notification request)  
       {  
           Console.WriteLine("\nNew Notification Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine(request.Info);  
           Console.WriteLine(request.Source);  
           Console.WriteLine(request.Type);  
           Console.WriteLine("*************************************************");  
  
           // Invoke th TableOp method in the TableOperation class  
           TableOperation Ops = new TableOperation();  
           Ops.TableOp();  
       }  
   }  
   ```  
  
4. 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据的连接 URI 的一部分，必须实现以下类用于传递 SQL Server 数据库的凭据。 在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。  
  
   ```  
   class NotificationCredentials : ClientCredentials, IServiceBehavior  
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
           ClientCredentials clone = new NotificationCredentials();  
           clone.UserName.UserName = this.UserName.UserName;  
           clone.UserName.Password = this.UserName.Password;  
           return clone;  
       }  
   }  
   ```  
  
5. 创建**SqlAdapterBinding**并配置适配器后，若要通过指定的绑定属性接收查询通知。 可以在代码中显式或配置中以声明方式执行此操作。 至少，您必须指定**InboundOperationType**并**NotificationStatement**绑定属性。  
  
   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
   binding.NotifyOnListenerStart = true;  
   ```  
  
6. 通过实例化指定的 SQL Server 数据库凭据**NotificationCredentials**步骤 4 中创建的类。  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  
  
7. 创建在步骤 3 中创建的 WCF 服务的实例。  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. 创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。 此外必须指定凭据。  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. 将服务终结点添加到服务主机。 若要执行此操作：  
  
   - 使用在步骤 5 中创建的绑定。  
  
   - 指定连接 URI，其中包含的凭据，如果需要，入站 id。  
  
   - 作为"NotificationOperation"指定的协定。  
  
     ```  
     // Add service endpoint: be sure to specify NotificationOperation as the contract  
     Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
     serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
     ```  
  
10. 若要接收通知消息，请打开服务主机。  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. 若要停止接收通知，请关闭服务主机。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>示例  
 下面的示例显示了.NET 应用程序以接收通知消息为 Employee 表。  
  
> [!NOTE]
>  下面的代码段实例化**TableOperation.cs**类，并调用**TableOp**方法。 步骤 1 中描述类和方法。  
  
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
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new NotificationCredentials();  
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
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)