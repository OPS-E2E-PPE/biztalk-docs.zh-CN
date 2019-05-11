---
title: 调用函数和使用 WCF 服务模型的 Oracle 数据库中的过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 097916c7fcf971563ef70c933e348c214aceeab5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529057"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a>调用函数和使用 WCF 服务模型的 Oracle 数据库中的过程
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]过程、 函数和包作为操作的图面。 在 WCF 服务模型中这些操作表示为 WCF 客户端上的方法。 WCF 服务模型和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   **支持函数**。 Oracle 函数的返回值显示为 WCF 客户端方法的返回值。 Oracle 参数作为参数 （使用适当的方向的定义如下） 提供给 WCF 客户端方法。  
  
-   **支持过程**。 OUT 参数 Oracle 过程的第一个显示为 WCF 客户端方法的返回值。 所有其他 Oracle 参数作为参数 （使用适当的方向的定义如下） 提供给 WCF 客户端方法。  
  
-   **支持 Oracle 包**。 操作的名称和其参数类型的命名空间进行限定按包名称。  
  
-   **支持重载函数和过程**。  
  
-   **支持 IN，OUT 和 OUT 参数的过程和函数的基本 Oracle 数据类型为 IN**。 OUT 参数显示为**出**WCF 客户端方法的参数和在 OUT 参数显示为**ref**参数。  
  
-   **支持 IN、 扩展，并在输出的过程和函数，以及函数返回值的 REF CURSOR 参数**。 有关详细信息，请参阅[执行的操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
-   **中支持，扩展，IN 出记录类型的过程和函数的参数，以及函数返回值**。 有关详细信息，请参阅[执行的操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 中的示例本主题使用 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 重载过程。 此过程从基于帐户 ID 或帐户名称 SCOTT/帐户表中读取一条记录。 使用 SDK 示例提供了一个脚本来生成此过程和表。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 下表显示的名称以及 WCF 客户端的过程，生成的方法的函数和包，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面。 除非重载函数或过程，单个 WCF 客户端用于调用的所有在架构中，所有架构中的过程或函数的所有函数和在包中的过程。  
  
|Oracle 项目|WCF 客户端操作名称|示例|  
|---------------------|-------------------------------|-------------|  
|过程|[SCHEMA]ProcedureClient.[PROC_NAME]|SCOTTProcedureClient.MYPROC|  
|函数|[SCHEMA]FunctionClient.[FUNC_NAME]|SCOTTProcedureClient.MYFUNC|  
|包 （过程或函数）|[架构]包 [PACKAGE_NAME] 客户端。[PROC_NAME 或 FUNC_NAME]|SCOTTPackageMYPACKAGEClient.MYPROC|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数; 的名称例如，MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 Oracle 记录类型参数和返回值，以及作为复杂包含 Oracle 记录的行数据 （或字段） 的 XML 类型返回的 REF CURSOR 参数的结果集。 在 WCF 服务模型中，每个 XML 类型表示为一个.NET 类;类的属性表示的字段的记录类型或 REF 游标结果集。 Oracle 记录类型始终表示为强类型化.NET 类。 REF CURSOR 结果集，但是，可以表示为强类型化或弱类型基于 REF CURSOR 本身是否声明为强类型化或弱类型的记录。 表示 REF CURSOR 或记录类型参数 （或返回值） 中基于过程、 函数或包的唯一命名空间中的生成的类。 下表显示了这些命名空间。  
  
|Oracle 项目|命名空间|示例|  
|---------------------|---------------|-------------|  
|过程|[BASE_NS]. [SCHEMA].Procedure.[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC|  
|函数|[BASE_NS]. [SCHEMA].Function.[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC|  
|包 （过程）|[BASE_NS]. [SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC|  
|包 （函数）|[BASE_NS]. [SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]|microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC|  
|通用记录集 （弱类型）|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 有关如何使用这些命名空间的记录参数的信息，请参阅[执行的操作使用记录的类型在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)。 有关如何使用这些命名空间的 REF CURSOR 参数的信息，请参阅[执行的操作使用 REF CURSOR 在 Oracle 数据库中使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)。  
  
 一般情况下，Oracle 参数和返回值被映射，如下所示中的 WCF 客户端方法：  
  
- Oracle IN 参数将映射到.NET （输入） 参数。  
  
- Oracle OUT 参数映射到.NET**出**参数。  
  
- Oracle 在 OUT 参数映射到.NET **ref**参数。  
  
- 函数返回值映射到方法的返回值。  
  
  但是，存在两个重要的例外情况：  
  
- Oracle IN 出 REF CURSOR 参数拆分输入的字符串和一个输出 (**出**) 记录集。 这是因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CUSROR 参数作为字符串，并为复杂类型 （记录集） 的出 REF CURSOR 参数，这些不能组合到单个参数。  
  
- OUT 参数在 Oracle 过程中的第一个映射到 WCF 客户端方法的返回值。 这是标准的 WCF 行为。  
  
  下面的示例演示 （SCOTT 架构中加载） 的简单 Oracle 过程的一部分而生成，以调用它的 WCF 客户端方法的签名。 Oracle 过程具有三个 IN 参数、 三个在 OUT 参数，和三个输出参数但是，WCF 客户端方法没有映射输出参数的第一个的参数。 相反，它将映射到方法的返回值。  
  
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
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持通过将唯一字符串追加到的节点 ID 和命名空间，它会显示出的每个重载的项目重载过程、 函数和包。 此字符串是"overload1"用于第一个重载，"overload2"下一步的重载，等等。  
  
 在 WCF 服务模型中由唯一的 WCF 客户端表示每个重载的过程或函数。 这不同于在架构中，在架构中，过程的所有函数的所有非过载情况或者的过程和函数在包中的所有调用的同一个 WCF 客户端。 下表显示 WCF 客户端名称和为重载的过程、 函数和包生成的方法。  
  
|Oracle 项目|WCF 客户端名称|示例|  
|---------------------|---------------------|-------------|  
|重载的包 （过程）|[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]|SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC|  
|重载的包 （函数）|[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]|SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC|  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [OVERLOAD_ID] = 标识重载的项目; 的唯一字符串"overload1"、"overload2"等。  
  
 下表显示了为重载的过程、 函数和包生成的命名空间。  
  
|Oracle 项目|命名空间|示例|  
|---------------------|---------------|-------------|  
|包 （过程）|[BASE_NS]. [SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1|  
|包 （函数）|[BASE_NS]. [SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]|microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1|  
|通用记录集 （弱类型）|[BASE_NS]|microsoft.lobservices.oracledb._2007._03|  
  
 [BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [PROC_NAME] = Oracle 过程; 的名称例如，MYPROC。  
  
 [FUNC_NAME] = Oracle 函数; 的名称例如 MYFUNC。  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [OVERLOAD_ID] = 标识重载的项目; 的唯一字符串"overload1"、"overload2"等。 在字符串中的数字值是由 Oracle 数据库维护的项目重载 ID。  
  
 下面的示例演示在 WCF 客户端和 ACCOUNT_PKG 包中的重载 GET_ACCOUNT 过程生成的方法签名。 （Oracle 声明包含。）此示例演示如何为每个重载生成唯一的 WCF 客户端和如何为每个客户端生成的方法返回的记录集的唯一命名空间中。  
  
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
 若要通过使用 WCF 客户端调用一个函数或过程，请执行以下步骤。  
  
1. 生成用于目标函数、 过程或包的 WCF 客户端类。 此类应包含将在目标项目调用操作方法。  
  
   > [!NOTE]
   >  在[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，重载函数和过程出现在**可用类别和操作**框为 [NAME].1、 [名称].2，[NAME].3，依次类推，其中 [名称] 是重载的项目和数字值的名称是对 Oracle 数据库的重载 ID。  
  
2. 创建 WCF 客户端类的实例并调用其方法调用的函数或过程。  
  
   有关更多详细信息，有关如何创建 WCF 客户端类，并在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[具有 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。  
  
   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle 数据库上执行一个事务内的每个操作。  
  
> [!IMPORTANT]
>  表示 REF CURSOR 和记录类型参数或返回值的函数或过程 （和包） 中的类为每个函数或过程声明中的唯一命名空间。 例如，这意味着，将为每个 WCF 客户端方法声明中唯一的命名空间用作中两个不同的函数的返回值的包 REF CURSOR 类型。 您必须声明不同的变量来保存这些不同的返回值或相应地转换该变量时调用的 WCF 客户端方法之一。  
  
 下面的示例演示如何调用重载的 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT 过程从 /SCOTT/ACCOUNT 表获取帐户记录。 首先通过调用 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 过程创建一个新的记录。 然后，读取新记录后两次通过调用 GET_ACCOUNT 的不同重载。 此示例使用三个 WCF 客户端，一个用于 CREATE_ACCOUNT 过程，分别用于 GET_ACCOUNT 重载。 使用别名来区分 GET_ACCOUNT 的返回值使用的命名空间。 可在 SDK 示例的完整示例。 有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)