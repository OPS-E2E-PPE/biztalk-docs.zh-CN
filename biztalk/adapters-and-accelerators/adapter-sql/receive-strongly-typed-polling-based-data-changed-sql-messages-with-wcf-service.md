---
title: 使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息 |Microsoft Docs
description: 使用.NET 应用程序配置类型化的轮询或使用 BizTalk Server 中的 WCF SQL 适配器使用 WCF 服务的强类型轮询
ms.custom: ''
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cbe58edcfcca4d149279cf91d30f8bbd4d3b55b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368207"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a>使用 WCF 服务模型从 SQL Server 接收强类型基于轮询的数据更改消息
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 接收强类型的轮询消息。 可以指定适配器轮询数据库将执行的轮询语句。 轮询语句可以是 SELECT 语句或存储的过程返回一个结果集。 在方案中必须使用强类型轮询你想要接收的强类型化结果集。 适配器如何支持强类型轮询的详细信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。  

> [!IMPORTANT]
>  如果想要在单个应用程序中有多个轮询操作，则必须指定**InboundID**连接属性连接 URI，使其成为唯一的一部分。 指定的入站的 ID 添加到要使其成为唯一的操作命名空间。  

## <a name="how-this-topic-demonstrates-polling"></a>本主题演示轮询的方式  
 本主题演示如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收强类型化数据更改消息、 创建.NET 应用程序和生成的 WCF 服务协定**TypedPolling**操作。 请确保指定以下内容时生成的 WCF 服务协定：  

- 必须指定**InboundID**连接 URI 的一部分。  

- 必须指定的轮询语句**PollingStatement**属性绑定。  

  此外，如果你想要指定其他轮询相关生成代理类时的绑定属性指定**PolledDataAvailableStatement**作为：  

```  
SELECT COUNT(*) FROM Employee  
```  

 **PolledDataAvailableStatement**必须返回的结果集包含正值的第一个单元格。 如果第一个单元格不包含正值，适配器将不会执行轮询语句。  

 轮询语句的一部分，请执行以下操作：  

1. 从 Employee 表选择所有行。  

2. 执行存储的过程 (MOVE_EMP_DATA) 将所有记录从 Employee 表移动到 EmployeeHistory 表。  

3. 执行存储的过程 (ADD_EMP_DETAILS) 若要将新记录添加到 Employee 表。 此过程将雇员姓名、 designation 和薪金作为参数。  

   若要执行这些操作，必须指定以下**PollingStatement**属性绑定在生成 WCF 服务协定和帮助程序类时：  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 执行轮询语句后，选择从 Employee 表的所有记录，并接收到来自 SQL Server 的消息。 MOVE_EMP_DATA 存储过程执行适配器后，所有这些记录会移到 EmployeeHistory 表。 然后，执行 ADD_EMP_DETAILS 存储过程以将新记录添加到 Employee 表。 下一次轮询执行将仅返回一条记录。 此循环将一直继续，直到您关闭服务主机。  

## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a>配置与 SQL 适配器的绑定属性的类型化的轮询  
 下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置要接收数据更改消息的适配器的属性。 以外**PollingStatement**绑定属性，在本部分中列出的所有其他绑定属性所需的.NET 应用程序在运行时。 必须指定**PollingStatement**之前生成的 WCF 服务协定绑定属性**TypedPolling**操作。  


|         绑定属性         |                                                                                                                                                                                                                                                                                              Description                                                                                                                                                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                             指定是否想要执行**轮询**， **TypedPolling**，或**通知**的入站操作。 默认值是**轮询**。 若要接收强类型的轮询消息，请将此设置为**TypedPolling**。                                                                                                                                                                                             |
| **PolledDataAvailableStatement** |                                                                                                                                           指定适配器执行以确定是否可用于轮询的任何数据的 SQL 语句。 SQL 语句必须返回的结果集由行和列组成。 仅为可用的行，如果指定的 SQL 语句**PollingStatement**将执行属性绑定。                                                                                                                                            |
|   **PollingIntervalInSeconds**   |                                                                              指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行该语句为指定**PolledDataAvailableStatement**属性绑定。 默认值为 30 秒。 轮询间隔确定连续轮询之间的时间间隔。 如果在指定时间间隔内执行该语句，则适配器将等待间隔中的剩余时间。                                                                              |
|       **PollingStatement**       | 指定要轮询 SQL Server 数据库表的 SQL 语句。 您可以指定简单的 SELECT 语句或存储的过程轮询语句。 默认值为 NULL。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**属性绑定。 可以指定任意数量的以分号分隔的 SQL 语句。 **重要提示：** 有关**TypedPolling**，生成元数据之前，必须指定此绑定属性。 |
|      **PollWhileDataFound**      |                                                                                 指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略的轮询间隔，并持续执行 SQL 语句为指定**PolledDataAvailableStatement**绑定属性，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。                                                                                 |

 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要轮询 SQL Server，请阅读更多。  

## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a>配置 WCF 服务模型中的强类型轮询  
 若要接收**轮询**操作使用 WCF 服务模型时，您必须：  

1. 为生成的 WCF 服务协定 （接口） **TypedPolling**从由适配器公开的元数据的操作。 若要执行此操作，可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。 在生成此示例中的 WCF 服务协定，请确保：  

   -   您指定**InboundID**作为**员工**。  

   -   指定的轮询语句**PollingStatement**属性绑定。 对于此示例中，指定轮询语句作为:  

       ```  
       SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
       ```  

2. 实现此接口中的 WCF 服务。  

3. 托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  

## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例轮询 Employee 表。 此示例还使用 MOVE_EMP_DATA 和 ADD_EMP_DETAILS 存储过程。 这些示例提供了一个脚本来生成这些项目。 有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **TypedPolling_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  

## <a name="the-wcf-service-contract-and-class"></a>WCF 服务约定和类  
 可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**TypedPolling**操作。 有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  

### <a name="the-wcf-service-contract-interface"></a>WCF 服务协定 （接口）  
 下面的代码演示 WCF 服务协定 （接口） 为生成**TypedPolling**操作。  

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
 通过修改消息协定命名空间**InboundID**中的连接 URI，如果指定的参数。 在此示例中，指定入站的 ID 作为**员工**。 请求消息返回强类型化结果集。  

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
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。 文件的名称是 SqlAdapterBindingService.cs。 您可以将逻辑来处理**TypedPolling**直接在此类操作。 下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

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

## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a>轮询操作接收强类型化的入站的消息  
 本部分说明了如何编写.NET 应用程序以接收使用强类型的入站的轮询消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  

1. 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**TypedPolling**操作。 请确保指定以下内容时生成此示例中的 WCF 服务协定：  

   - 必须指定**InboundID**作为**员工**。  

   - 必须指定的轮询语句**PollingStatement**属性绑定。 对于此示例中，指定轮询语句作为:  

     ```  
     SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
     ```  

     有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。 在生成服务协定和帮助程序类时，可以选择指定的绑定属性。 这可确保它们正确设置生成的配置文件中。  

2. 实现在步骤 1 中生成的接口和帮助程序类中的 WCF 服务。 **TypedPolling**此类方法可以处理从接收的数据中遇到错误时引发异常中止轮询事务**TypedPolling**操作; 否则为方法不返回任何内容。 必须按如下所示属性的 WCF 服务类：  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    内**TypedPolling**方法，可以直接实现应用程序逻辑。 可以 SqlAdapterBindingService.cs 中找到此类。 此代码在此示例中的嵌套类**SqlAdapterBindingService**类。 在此代码中，作为强类型化结果集接收轮询消息写入控制台。  

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

3. 因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据的连接 URI 的一部分，必须实现以下类用于传递 SQL Server 数据库的凭据。 在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。  

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

4. 创建**SqlAdapterBinding**和配置轮询操作时，指定的绑定属性。 可以在代码中显式或配置中以声明方式执行此操作。 至少，您必须指定**InboundOperationType**， **PolledDataAvailableStatement**，并**PollingStatement**。  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.TypedPolling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. 通过实例化指定的 SQL Server 数据库凭据**PollingCredentials**步骤 3 中创建的类。  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. 创建在步骤 2 中创建的 WCF 服务的实例。  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. 创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。 基本连接 URI 不能包含入站 id。 此外必须指定凭据。  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. 将服务终结点添加到服务主机。 若要执行此操作：  

   -   使用在步骤 4 中创建的绑定。  

   -   指定连接 URI，其中包含的凭据，如果需要，入站 id。  

   -   作为"TypedPolling_Employee"指定的协定。  

   ```  
   // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
   serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
   ```  

9. 若要接收轮询数据，请打开服务主机。 只要查询返回结果集，则适配器将返回数据。  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. 若要终止轮询，关闭服务主机。  

    > [!IMPORTANT]
    >  该适配器将继续轮询，直到关闭服务主机。  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a>示例  
 下面的示例演示执行 Employee 表的轮询查询。 轮询语句将执行以下任务：  

1. 从 Employee 表中选择的所有记录。  

2. 执行上述 MOVE_EMP_DATA 存储过程以将所有记录从 Employee 表都移动到 EmployeeHistory 表。  

3. 执行上述 ADD_EMP_DETAILS 存储过程以将一条记录添加到 Employee 表。  

   第一个轮询消息将包含从 Employee 表的所有记录。 后续轮询消息将包含仅由 ADD_EMP_DETAILS 存储过程插入的最后一条记录。 适配器将继续轮询，直到按关闭服务主机`<RETURN>`。  

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

## <a name="see-also"></a>请参阅  
 [SQL 适配器使用 WCF 服务模型轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
