---
title: "使用 WCF 服务模型使用 SELECT 语句的轮询 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2cac950ced0fb0d7133e99bc3d12699f9379bcb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a>使用 WCF 服务模型使用 SELECT 语句的轮询 Oracle E-business Suite
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要通过使用 SELECT 语句持续轮询接口表接收定期的数据更改消息，接口视图、 表和 Oracle E-business Suite 中的视图。 你可以指定为适配器执行定期轮询 Oracle E-business Suite 的轮询语句的 SELECT 语句。 你还可以指定后轮询 PL/SQL 代码块适配器执行执行轮询语句后。  
  
 若要启用轮询，必须指定某些绑定属性，如本主题中所述。  有关如何适配器支持轮询的详细信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>使用 Oracle E-business Suite 适配器绑定属性中配置的轮询操作  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]更改消息的绑定属性，用于配置适配器，以接收数据。 在运行轮询应用程序时，必须指定这些绑定属性。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定是否想要执行**轮询**或**通知**入站操作。 默认值是**轮询**。|  
|**PolledDataAvailableStatement**|指定适配器以确定任何数据是否可用于轮询将执行的 SQL 语句。 仅当一条记录时，SELECT 语句你为指定**PollingInput**将执行绑定属性。|  
|**PollingInterval**|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器休眠的剩余时间的时间间隔内。|  
|**PollingInput**|指定的轮询语句。 若要轮询使用 SELECT 语句，必须指定此绑定属性的 SELECT 语句。 默认值为 null。<br /><br /> 必须指定的值**PollingInput**绑定属性来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。|  
|**PollingAction**|指定轮询操作的操作。 你可以确定此轮询操作的生成操作使用的服务接口[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。|  
|**PostPollStatement**|指定在指定的语句之后执行的语句块**PollingInput**绑定属性执行。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略轮询间隔和连续执行轮询语句中，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行轮询语句按照指定的轮询间隔。 默认值为 false。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要轮询的 Oracle 数据库，进一步阅读。  
  
## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收数据的支持更改使用 SELECT 语句的消息，轮询**MS_SAMPLE_EMPLOYEE**接口中的表**应用程序对象库**应用程序。 运行示例后，在 Oracle E-business Suite 中创建这些对象提供的 create_apps_artifacts.sql 脚本时创建此表。  
  
 为了演示轮询操作，我们执行以下操作：  
  
-   指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性以确定其中接口表轮询 (MS_SAMPLE_EMPLOYEE) 有任何数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     这可确保仅当 MS_SAMPLE_EMPLOYEE 接口表具有某些记录时，适配器都将执行轮询语句。  
  
-   指定 SELECT 语句，以**PollingInput**绑定属性。 此语句将检索 MS_SAMPLE_EMPLOYEE 接口表中的所有行。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  有关 FOR UPDATE 子句的 SELECT 语句中使用的信息，请参阅[从 Oracle E-business Suite 接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)。  
  
-   指定作为的一部分的 DELETE 语句**PostPollStatement**绑定属性。 此语句将从 MS_SAMPLE_EMPLOYEE 接口表中删除所有数据。 在此示例中，你可以设置为此绑定属性：  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     发生这种情况后下, 一次为指定的语句**PollingInput**将执行，它将不提取任何数据。  
  
-   直到更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，因此必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新记录将不会获取任何轮询消息。 你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>在 WCF 服务模型中配置轮询  
 若要轮询界面表使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 WCF 服务模型，你必须：  
  
-   为生成的 WCF 服务协定 （接口）**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-   实现此接口从 WCF 服务。  
  
-   托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例轮询 MS_SAMPLE_EMPLOYEE 接口表。 在示例提供了一个脚本以生成表。 有关这些示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **SelectPolling_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF 服务协定和类  
 你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**轮询**操作。 有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示为生成的 WCF 服务协定 （接口）**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  
  
### <a name="the-message-contracts"></a>消息协定  
 以下是消息协定**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  
  
    public Poll() {  
    }  
  
    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF 服务类  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。 文件的名称是 OracleEBSBindingService.cs。 你可以将插入的逻辑来处理**轮询**直接插入此类操作。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a>使用 SELECT 语句的轮询操作接收入站的消息  
 此部分提供有关如何编写.NET 应用程序以接收使用的入站的轮询消息说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
#### <a name="to-receive-polling-messages-using-a-select-statement"></a>若要接收使用 SELECT 语句的轮询消息  
  
1.  使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**轮询**MS_SAMPLE_EMPLOYEE 接口表上的操作。 有关详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。 生成服务协定和帮助程序类时，可以选择指定的绑定属性。 这可确保它们正确设置生成的配置文件中。  
  
2.  实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。 **轮询**此类的方法可以处理从接收的数据遇到错误时引发异常中止轮询事务，**轮询**操作; 否则该方法将不执行返回任何内容。 必须属性 WCF 服务类，如下所示：  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     在**轮询**方法，你可以直接实现你的应用程序逻辑。 OracleEBSBindingService.cs 中找不到此类。 此示例中的此代码子类**OracleEBSBindingService**类。 在此代码中，轮询接收该消息，写入控制台。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  必须实现以下类用于避免将凭据传递作为 URI 的一部分。 在应用程序的后半部分，将实例化此类，以传递凭据。  
  
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
  
4.  创建**OracleEBSBinding**和通过指定绑定属性中配置的轮询操作。 可以在代码中显式或配置中以声明方式执行此操作。 至少，你必须指定**InboundOperationType**， **PolledDataAvailableStatement**， **PollingInput**，和**PollingAction**绑定属性。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
5.  因为轮询接口表，你还必须设置应用程序上下文。 有关应用程序上下文和所需的设置应用程序上下文的绑定属性的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  指定 Oracle E-business Suite 凭据，方法是实例化**PollingCredentials**在步骤 3 中创建的类。  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  创建在步骤 2 中创建的 WCF 服务的实例。  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
8.  创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。 如果指定，则基连接 URI 不能包含的入站的 ID。 你还必须在此处传递凭据。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. 将服务终结点添加到服务主机。 为此，请执行以下操作：  
  
    -   使用在步骤 4 中创建的绑定。  
  
    -   指定连接 URI，其中包含凭据，如果需要，一个入站的 id。  
  
    -   作为"InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE"轮询 MS_SAMPLE_EMPLOYEE 接口表中指定的协定。  
  
    ```  
    // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
    ```  
  
10. 若要接收轮询数据，请打开服务主机。 每当查询返回一个结果集，该适配器将返回数据。  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
11. 若要终止轮询，关闭服务主机。  
  
    > [!IMPORTANT]
    >  适配器将继续轮询，直到关闭服务主机。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>示例  
 下面的示例演示的轮询应用程序轮询 MS_SAMPLE_EMPLOYEE 接口表。 **PollingInput**属性包含从 MS_SAMPLE_EMPLOYEE 表中读取所有数据的 select 语句和 post 轮询语句从同一个表中删除所有数据。 第一条的轮询消息从 MS_SAMPLE_EMPLOYEE 接口表提供的所有记录。 后续的轮询消息将不包含任何记录，因为 post 轮询语句删除记录。 直到更多的数据添加到 MS_SAMPLE_EMPLOYEE 接口表，则将无法获得任何轮询消息。 因此，你必须重新填充 MS_SAMPLE_EMPLOYEE 接口表与新记录。 你可以通过运行这些示例使用提供的 insert_apps_data.sql 脚本来实现。 运行此脚本后下, 一个轮询操作将获取新记录插入到表。 适配器将继续轮询，直到按关闭服务主机`<RETURN>`。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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
 [使用 WCF 服务模型的轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)