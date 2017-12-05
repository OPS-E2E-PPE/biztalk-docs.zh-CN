---
title: "调用函数和 Oracle 数据库使用 WCF 服务模型中的过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f1fac59fc77b0cf52abe789db8feb2305043708
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a>调用函数和 Oracle 数据库使用 WCF 服务模型中的过程
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现过程、 函数和包作为操作。 在 WCF 服务模型会将这些操作表示为 WCF 客户端上的方法。 WCF 服务模型和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   **支持函数**。 Oracle 函数的返回值呈现为 WCF 客户端方法的返回值。 Oracle 参数作为 （与相应的方向定义下面） 的参数提供给 WCF 客户端方法。  
  
-   **支持过程**。 OUT 参数 Oracle 过程的第一个呈现为 WCF 客户端方法的返回值。 所有其他 Oracle 参数作为 （与相应的方向定义下面） 的参数提供给 WCF 客户端方法。  
  
-   **支持 Oracle 包**。 该操作的名称和其参数类型的命名空间是由包名称限定的。  
  
-   **支持重载函数和过程**。  
  
-   **支持 IN、 OUT 和 IN 出的过程和函数的基本 Oracle 数据类型的参数**。 OUT 参数中加以表示为**出**作为 WCF 客户端方法的参数和 IN OUT 参数进行展示**ref**参数。  
  
-   **支持 IN、 扩展和 IN 出过程和函数，以及函数返回值的 REF CURSOR 参数**。 有关详细信息，请参阅[执行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
-   **中支持，扩展和 IN 出记录类型参数的过程和函数，以及函数返回值**。 有关详细信息，请参阅[执行操作使用记录类型使用 WCF 服务模型的 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 中的示例此主题使用 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 重载过程。 此过程从基于帐户 ID 或帐户名称 SCOTT/帐户表中读取一条记录。 一个脚本来生成此过程和下表提供的 SDK 示例。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 下表显示 WCF 客户端和有关过程，生成的方法的名称的函数和包[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面。 除非函数或过程重载函数，单个 WCF 客户端用于调用的所有在架构中，所有在架构中，过程或函数的所有函数和包中的过程。  
  
|Oracle 项目|WCF 客户端操作名称|示例|  
|---------------------|-------------------------------|-------------|  
|过程|[架构]ProcedureClient。[PROC_NAME]|SCOTTProcedureClient.MYPROC|  
|函数|[架构]FunctionClient。[FUNC_NAME]|SCOTTProcedureClient.MYFUNC|  
|包 （过程或函数）|[架构]包 [包名称] 客户端。[PROC_NAME 或 FUNC_NAME]|SCOTTPackageMYPACKAGEClient.MYPROC|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数中; 的名称例如，MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 Oracle 记录类型参数和返回值，以及返回 REF CURSOR 参数作为包含 Oracle 记录的行数据 （或字段） 的复杂 XML 类型的结果集。 在 WCF 服务模型中，上述每种 XML 类型表示为一个.NET 类;类的属性表示记录类型或 REF CURSOR 结果集的字段。 Oracle 记录类型始终表示为强类型化.NET 类。 REF CURSOR 结果集，但是，可以表示为强类型化或弱类型基于 REF CURSOR 本身是否声明为强类型化或弱类型的记录。 表示 REF CURSOR 或记录类型参数 （或返回值） 中一个基于过程、 函数或包的唯一命名空间中的生成的类。 下表显示这些命名空间。  
  
|Oracle 项目|命名空间|示例|  
|---------------------|---------------|-------------|  
|过程|[BASE_NS]。 [架构]。过程。[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT。Procedure.MYPROC|  
|函数|[BASE_NS]。 [架构]。函数。[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT。Function.MYFUNC|  
|包 （过程）|[BASE_NS]。 [架构]。包。[PACKAGE_NAME]。[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYPROC|  
|包 （函数）|[BASE_NS]。 [架构]。包。[PACKAGE_NAME]。[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYFUNC|  
|泛型记录集 （弱类型）|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = 基适配器命名空间;microsoft.lobservices.oracledb._2007._03。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 有关如何将这些命名空间用于记录参数的信息，请参阅[执行操作使用记录类型使用 WCF 服务模型的 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。 有关如何将这些命名空间用于 REF CURSOR 参数的信息，请参阅[执行操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
 一般情况下，Oracle 参数和返回值映射，如下所示的 WCF 客户端方法中：  
  
-   Oracle IN 参数映射到.NET （输入） 参数。  
  
-   Oracle OUT 参数映射到.NET**出**参数。  
  
-   Oracle IN OUT 参数映射到.NET **ref**参数。  
  
-   函数返回值将映射到方法的返回值。  
  
 但是，存在两个重要的例外：  
  
-   Oracle IN 出 REF CURSOR 参数将被拆分为输入的字符串和输出 (**出**) 记录集。 这是因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CUSROR 参数作为字符串，并为复杂类型 （记录集） 的出 REF CURSOR 参数，不能这些组合到单个参数。  
  
-   先出 Oracle 过程中的参数映射到的 WCF 客户端方法的返回值。 这是标准的 WCF 行为。  
  
 下面的示例演示一个简单的 Oracle 过程 （SCOTT 架构中加载） 过程的一部分和生成来调用它的 WCF 客户端方法的签名。 Oracle 过程具有三个 IN 参数、 三个 IN OUT 参数，和三个 OUT 参数;但是，WCF 客户端方法未映射的第一个输出参数的参数。 而被映射到方法的返回值。  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime\> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime\> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime\> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a>对重载的过程、 函数和包的支持  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持通过将是唯一的字符串追加到的节点 ID 和命名空间，它会显示为每个重载的项目重载过程、 函数和包。 此字符串为"overload1"的第一个重载，"overload2"下一步重载中，依次类推。  
  
 WCF 服务模型中由唯一的 WCF 客户端表示每个重载的过程或函数。 这是不同于在架构中，所有在架构中，过程的函数的所有的非重载情况或所有的过程和函数在包中的都同一个 WCF 客户端通过调用。 下表显示 WCF 客户端名称和为重载的过程、 函数和包生成的方法。  
  
|Oracle 项目|WCF 客户端名称|示例|  
|---------------------|---------------------|-------------|  
|重载的包 （过程）|[架构]包 [PACKAGE_NAME] [PROC_NAME]] [OVERLOAD_ID] 客户端。[PROC_NAME]|SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC|  
|重载的包 （函数）|[架构]包 [PACKAGE_NAME] [FUNC_NAME]] [OVERLOAD_ID] 客户端。[FUNC_NAME]|SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [OVERLOAD_ID] = 标识重载的项目中; 的唯一字符串"overload1"、"overload2"，依次类推。  
  
 下表显示为重载的过程、 函数和包生成的命名空间。  
  
|Oracle 项目|命名空间|示例|  
|---------------------|---------------|-------------|  
|包 （过程）|[BASE_NS]。 [架构]。包。[PACKAGE_NAME]。[PROC_NAME][OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYPROC.overload1|  
|包 （函数）|[BASE_NS]。 [架构]。包。[PACKAGE_NAME]。[FUNC_NAME]。[OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT。Package.MYPACKAGE.MYFUNC.overload1|  
|泛型记录集 （弱类型）|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = 基适配器命名空间;microsoft.lobservices.oracledb._2007._03。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数中; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [OVERLOAD_ID] = 标识重载的项目中; 的唯一字符串"overload1"、"overload2"，依次类推。 在字符串中的数字值是由 Oracle 数据库维护的项目重载 ID。  
  
 下面的示例演示 WCF 客户端和 ACCOUNT_PKG 包中的重载 GET_ACCOUNT 过程生成的方法签名。 （Oracle 声明是包含。）此示例演示如何为每个重载生成唯一的 WCF 客户端和如何为每个客户端生成的方法返回的记录集的唯一命名空间中。  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a>调用函数和过程  
 若要使用 WCF 客户端调用一个函数或过程，请执行以下步骤。  
  
1.  生成用于目标函数、 过程或包的 WCF 客户端类。 此类应包含的操作，将在目标项目上调用的方法。  
  
    > [!NOTE]
    >  在[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，重载函数和过程出现在**可用类别和操作**框以 [名称].1、 [名称].2，[NAME].3，依次类推，其中 [名称] 是重载的项目和的数字值的名称是对 Oracle 数据库的重载 ID。  
  
2.  创建 WCF 客户端类的实例并调用其方法来调用的函数或过程。  
  
 有关详细信息，有关如何创建一个 WCF 客户端类，在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库执行事务内的每个操作。  
  
> [!IMPORTANT]
>  表示 REF CURSOR 和记录类型参数或返回值函数或过程 （和包） 中的类为每个函数或过程声明中的唯一命名空间。 例如，这意味着，每个 WCF 客户端方法中，用作两个不同函数中的返回值的包 REF CURSOR 类型将唯一的命名空间中声明。 您必须声明单独的变量以保存这些不同的返回值或相应地转换该变量，在调用 WCF 客户端方法之一时。  
  
 下面的示例演示如何调用的重载的 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 过程从 /SCOTT/ACCOUNT 表中获取的客户记录。 首先通过调用 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 过程中创建新的记录。 请阅读新记录后两次通过调用 GET_ACCOUNT 的不同重载。 此示例使用三个 WCF 客户端，一个用于 CREATE_ACCOUNT 过程，两个分别用于 GET_ACCOUNT 重载。 使用别名来区分命名空间用于 GET_ACCOUNT 的返回值。 完整示例位于 SDK 示例。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)