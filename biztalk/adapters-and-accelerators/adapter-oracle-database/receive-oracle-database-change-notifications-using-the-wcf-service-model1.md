---
title: "接收使用 WCF 服务 Model1 Oracle 数据库更改通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0f0e2bf-3e76-43cc-85dc-7483dbce1cb5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed8723cef3351420cbe35e0f9fc85d2ba400b410
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-database-change-notifications-using-the-wcf-service-model1"></a>接收使用 WCF 服务 Model1 Oracle 数据库更改通知
本主题演示如何配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收查询通知消息。 为了演示通知，考虑一个表，ACCOUNTACTIVITY，与"处理"列。 一条新记录插入到此表时，状态列的值设置为 ' n '。 你可以配置要通过使用 SQL 语句，以检索具有与"处理"列的所有记录的通知注册接收通知的适配器 ' n '。 你可以通过指定的 SQL 语句来实现**NotificationStatement**绑定属性。 一旦适配器客户端收到通知，它可以包含执行对 Oracle 数据库的任何后续任务的逻辑。 在此示例中，为简单起见，适配器客户端列出具有的"处理"列的表中的所有记录 ' n '。  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a>与 Oracle 数据库适配器绑定属性中配置通知  
 下表总结了[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，用于配置从 Oracle 数据库接收通知。 在运行.NET 应用程序以接收通知时，必须指定这些绑定属性。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。|  
|**NotificationStatement**|指定用来注册查询通知的 SELECT 语句。 仅当指定的 SELECT 语句更改的结果集时，适配器获取一条通知消息。|  
|**NotifyOnListenerStart**|指定启动侦听器时，适配器是否发送到适配器客户端通知。|  
  
 有关这些属性的更完整说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。 有关如何使用的完整说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]若要从 Oracle 数据库接收通知，请阅读更多。  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>使用 WCF 服务模型配置通知  
 若要接收使用 WCF 服务模型的通知，你必须：  
  
-   为生成的 WCF 服务协定 （接口）**通知**从适配器公开的元数据的操作。 若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-   生成的 WCF 客户端**选择**ACCOUNTACTIVITY 表上的操作。 若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-   实现此接口从 WCF 服务。  
  
-   托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF 服务协定和类  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**通知**操作。 有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示为生成的 WCF 服务协定 （接口）**通知**操作。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="Notification_OperationGroup")]  
public interface Notification_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
    // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>消息协定  
 下面是通知操作的消息协定。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF 服务类  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。 文件的名称是 OracleDBBindingService.cs。 你可以将插入的逻辑来处理**通知**直接插入此类操作。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : Notification_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
        // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-database-change-notifications-using-wcf-service-model"></a>使用 WCF 服务模型的接收数据库更改通知  
 本部分将说明了如何编写.NET 应用程序以接收查询通知使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
#### <a name="to-receive-query-notifications"></a>若要接收查询通知  
  
1.  使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 客户端**选择**操作**ACCOUNTACTIVITY**表。 此客户端将用于接收通知邮件后执行选择操作。 添加新类，TableOperation.cs 到你的项目并添加下面的代码段，以执行选择操作。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        class TableOperation  
        {  
            public void TableOp()  
            {  
                //////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
                //////////////////////////////////////////////////////////////////////  
  
                SCOTT_Table_ACCOUNTACTIVITYClient client = new SCOTT_Table_ACCOUNTACTIVITYClient("OracleDBBinding_SCOTT_Table_ACCOUNTACTIVITY");  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
  
                ////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                //////////////////////////////////////////////////////////////////////  
                try  
                {  
                    Console.WriteLine("Opening the client ...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ////////////////////////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED VALUE  
                ////////////////////////////////////////////////////////////////////////////////////////  
  
                Console.WriteLine("The application will now select the last inserted record");  
  
                microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added records are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                    Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                    Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
            }  
        }  
    }  
  
    ```  
  
2.  使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**通知**操作。  
  
     有关详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。 生成服务协定和帮助程序类时，可以选择指定的绑定属性。 这可确保它们正确设置生成的配置文件中。  
  
3.  实现 WCF 服务从在步骤 2 中生成的接口和帮助程序类。 **通知**此类的方法可以处理从接收的数据遇到错误时引发异常中止操作，**通知**操作; 否则该方法将执行不返回任何内容。 必须属性 WCF 服务类，如下所示：  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     在**通知**方法，你可以直接实现你的应用程序逻辑。 OracleDBBindingService.cs 中找不到此类。 此示例中的此代码子类**OracleDBBindingService**类。 在此代码中，接收的通知消息写入控制台。 此外， **TableOp**方法内的**TableOperation**类调用以执行选择操作。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
        public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
    ```  
  
4.  必须实现以下类用于传递 Oracle 数据库的凭据。 在应用程序的后半部分，将实例化此类，以传递凭据。  
  
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
  
5.  创建**OracleDBBinding**并配置适配器后，若要通过指定绑定属性接收查询通知。 可以在代码中显式或配置中以声明方式执行此操作。 至少，你必须指定**InboundOperationType**和**NotificationStatement**绑定属性。  
  
    ```  
    OracleDBBinding binding = new OracleDBBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
    binding.NotifyOnListenerStart = true;  
    binding.NotificationPort = 10;  
    ```  
  
    > [!IMPORTANT]
    >  值**NotificationPort**绑定属性必须设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkId=196959](http://go.microsoft.com/fwlink/?LinkId=196959)。  
  
    > [!IMPORTANT]
    >  如果你未设置**NotificationPort**绑定属性，该适配器将假定默认值为-1 表示此绑定属性。 在这种情况下，你将需要完全禁用 Windows 防火墙，以接收通知消息。  
  
6.  指定 Oracle 数据库凭据，方法是实例化**NotificationCredentials**在步骤 4 中创建的类。  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "SCOTT";  
    credentials.UserName.Password = "TIGER";  
    ```  
  
7.  创建在步骤 3 中创建的 WCF 服务的实例。  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。 你还必须指定此处的凭据。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. 将服务终结点添加到服务主机。 为此，请执行以下操作：  
  
    -   使用在步骤 5 中创建的绑定。  
  
    -   指定连接 URI，其中包含凭据，如果需要，一个入站的 id。  
  
    -   作为"Notification_OperationGroup"指定的协定。  
  
    ```  
    // Add service endpoint: be sure to specify Notification_OperationGroup as the contract  
    Uri ConnectionUri = new Uri("oracledb://adapter");  
    serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
    ```  
  
10. 若要接收通知消息，请打开服务主机。  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. 若要停止接收通知，关闭服务主机。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>示例  
 下面的示例演示.NET 应用程序以接收 ACCOUNTACTIVITY 表的通知消息。  
  
> [!NOTE]
>  下面的代码段实例化**TableOperation.cs**类并调用**TableOp**方法。 类和方法所述步骤 1。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracledb://adapter");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
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
 [开发使用 WCF 服务模型的 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)