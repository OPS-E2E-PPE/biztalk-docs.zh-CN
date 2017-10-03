---
title: "使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd36081bd92c3bfae13916ed7d984fcd5de9763f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a>使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息
你可以配置[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]接收基于轮询的数据更改消息所依据的 Oracle 表或视图。 若要接收数据更改的消息，该适配器定期执行针对一个 Oracle 表或视图后, 跟一个可选的 PL/SQL 代码块的 SQL 查询。 然后返回 SQL 查询的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到应用程序作为强类型的结果集在入站 POLLINGSTMT 操作中。 有关用于配置和对 Oracle 执行轮询机制的详细信息数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。 我们强烈建议你阅读然后再继续本主题。  
  
 若要接收 POLLINGSTMT 操作，当使用 WCF 服务模型时，你必须：  
  
-   POLLINGSTMT 操作从适配器公开的元数据生成 WCF 服务协定 （接口）。 若要执行此操作，请使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe)。  
  
-   实现此接口从 WCF 服务。  
  
-   托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
 本部分中的主题提供信息和过程来帮助你对 Oracle 数据库表和视图的 WCF 服务模型中执行轮询。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例使用 /SCOTT/ACCOUNTACTIVITY 表和 /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY 函数。 一个脚本来生成这些项目附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>在 WCF 服务模型中配置轮询  
 你配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]设置绑定属性和一个可选的连接属性 （参数） 对 Oracle 数据库表和视图执行轮询。 其中一些属性是必需的并且某些，产生任何影响，同时在设计时和运行时就必须设置。  
  
-   在设计时连接参数和绑定属性时设置连接到 Oracle 数据库生成的 WCF 服务协定。  
  
-   在运行时用于创建服务主机的 OracleDBBinding 对象上设置绑定属性。 向服务主机添加服务侦听器时设置的连接参数。  
  
 以下列表提供的绑定属性和连接参数用于配置轮询的简要概述：  
  
-   **PollingStatement**绑定属性。 在设计时和在运行时，必须设置此绑定属性。  
  
-   可选的绑定的属性。 这些只需在运行时设置。  
  
-   **AcceptCredentialsInUri**绑定属性。 必须将此绑定属性设置为**true**在运行期间如果你想要启用连接 URI 中的凭据。 将服务终结点添加到服务主机时，用户名和密码必须处在连接 URI。  
  
-   **PollingId**查询中连接 URI 的字符串参数。 如果你想要更改 POLLINGSTMT 操作的命名空间，则必须设置此连接属性同时在设计时和运行时。  
  
 绑定属性以及用于配置轮询的连接参数的完整说明，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF 服务协定和类  
 您使用两个[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 来创建 WCF 服务协定 （接口），并支持 POLLINGSTMT 操作的类。  
  
 当您连接到 Oracle 数据库使用这些工具来生成服务协定 POLLINGSTMT 操作之一：  
  
-   必须指定**PollingStatement**绑定属性。 适配器使用 SELECT 语句中此绑定属性生成 POLLINGSTMT 操作返回的强类型化结果集的正确元数据。  
  
-   在连接 URI 中，可以选择指定 PollingId 参数。 适配器使用此参数来生成 POLLINGSTMT 操作的命名空间。  
  
 在下面的示例：  
  
-   **PollingStatement**设置为"选择 * 从 ACCOUNTACTIVITY FOR UPDATE"。  
  
-   **PollingId**设置为"AcctActivity"。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示为 POLLINGSTMT 操作生成的 WCF 服务协定 （接口）。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a>消息协定  
 由连接 URI 中的 PollingId 参数修改消息协定命名空间。 请求消息返回一组强类型的记录。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a>数据协定 Namespace  
 数据协定是一项服务以抽象方式描述要交换的数据的客户端之间达成的正式协议。 也就是说，以便进行通信，客户端和服务不必共享相同的类型，只是相同的数据协定。  
  
 发生数据更改消息，数据协定命名空间，你还要修改由 PollingId 参数 （如果指定） 中连接 URI。 数据协定组成一个类，表示查询结果集中的强类型的记录。 在此示例中省略类定义的详细信息。 此类包含表示在结果集中的列的属性。  
  
 在以下示例中，使用 PollingId"AcctActivity"。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF 服务类  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。 文件的名称是 OracleDBBindingService.cs。 你可以将插入的逻辑来处理此类直接 POLLINGSTMT 操作。 如果使用 svcutil.exe 来生成服务协定接口，则必须自行实现此类。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a>接收 POLLINGSTMT 操作  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a>从 Oracle 数据库适配器接收轮询数据  
  
1.  使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或 svcutil.exe 生成 WCF 服务协定 （接口），并用于 POLLINGSTMT 操作帮助器类。 有关详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。 至少，你必须将设置**PollingStatement**绑定时连接到该适配器的属性。 在连接 URI 中，可以选择指定 PollingId 参数。 如果你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，你应设置你的配置所必需的所有绑定参数。 这可确保它们正确设置生成的配置文件中。  
  
2.  实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。 此类的 POLLINGSTMT 方法可能会引发异常中止轮询事务，如果遇到错误则处理从 POLLINGSTMT 操作; 接收的数据否则该方法不返回任何内容。 必须属性 WCF 服务类，如下所示：  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  如果你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要生成界面，可以实现你的逻辑直接在**POLLINGSTMT**中生成方法**OracleDBBindingService**类。 OracleDBBindingService.cs 中找不到此类。 此示例中的此代码子类**OracleDBBindingService**类。  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
        public class PollingStmtService : OracleDBBindingService  
        {  
            public override void POLLINGSTMT(POLLINGSTMT request)  
            {  
                Console.WriteLine("\nNew Polling Records Received");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                        request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                        request.POLLINGSTMTRECORD[i].AMOUNT,  
                                        request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                        request.POLLINGSTMTRECORD[i].DESCRIPTION);  
                }  
            }  
        }  
        ```  
  
    2.  如果使用 svcutil.exe 来生成界面，你必须创建 WCF 服务实现的接口和实现你的逻辑中**POLLINGSTMT**此类的方法。  
  
3.  创建在步骤 2 中创建的 WCF 服务的实例。  
  
    ```  
    // create service instance  
    PollingStmtService pollingInstance = new PollingStmtService();  
    ```  
  
4.  创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。 Userinfoparams 或 query_string，不能包含基连接 URI。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  创建**OracleDBBinding**和通过设置其绑定属性中配置的轮询操作。 可以在代码中显式或配置中以声明方式执行此操作。 至少，你必须指定轮询语句和轮询间隔。 在此示例中，你指定的凭据作为 URI 的一部分以便还必须设置**AcceptCredentialsInUri**到**true**。  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    OracleDBBinding binding = new OracleDBBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
  
    // Same as statement specified in Configure Adapter dialog box  
    binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
    // Be sure to set the interval long enough to complete processing before  
    // the next poll  
    binding.PollingInterval = 15;  
    // Polling is transactional; be sure to set an adequate isolation level   
    // for your environment  
    binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
    ```  
  
6.  将服务终结点添加到服务主机。 为此，请执行以下操作：  
  
    -   使用在步骤 5 中创建的绑定。  
  
    -   指定连接 URI，其中包含凭据并根据需要 PollingId。  
  
    -   作为"POLLINGSTMT_OperationGroup"指定的协定。  
  
    ```  
    // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
    Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
    srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
    ```  
  
7.  若要接收轮询数据，请打开服务主机。 每当查询返回一个结果集，该适配器将返回数据。  
  
    ```  
    // Open the service host to begin polling  
    srvHost.Open();  
    ```  
  
8.  若要终止轮询，关闭服务主机。  
  
    > [!IMPORTANT]
    >  适配器将继续轮询，直到关闭服务主机。  
  
    ```  
    srvHost.Close();  
    ```  
  
### <a name="example"></a>示例  
 下面的示例演示针对/SCOTT/ACCOUNTACTIVITY 表执行的轮询查询。 后轮询语句调用将处理的记录移到另一个表 /SCOTT/ACCOUNTHISTORY Oracle 函数。 要修改 POLLINGSTMT 操作的命名空间，请在连接 URI 中设置"AccountActivity"的 PollingId 参数。 在此示例中，通过子类分类生成创建 POLLINGSTMT 操作的 WCF 服务**OracleDBBindingService**类; 但是，你可以直接在生成的类中实现你的逻辑。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发使用 WCF 服务模型的 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)