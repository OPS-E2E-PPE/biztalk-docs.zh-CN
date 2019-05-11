---
title: 使用 WCF 服务模型的 Oracle 数据库中运行的操作使用的记录类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31785fd5c804e7f599b575678f1f57d60fcf8ebe
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528870"
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a>使用 WCF 服务模型的 Oracle 数据库中运行的操作使用的记录类型
Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。 在 WCF 服务模型中，记录类型都反序列化为强类型化.NET 类。 记录字段表示为类的属性。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持以下类型的记录类型：  
  
- 声明为表 %行类型参数在存储的过程和函数中的记录类型。  
  
- 例如，声明为类型的记录参数 PL/SQL 包中的记录类型 `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`  
  
- 包含嵌套的记录的记录类型。  
  
- 缩小，显示作为中的记录类型或为过程或函数在 OUT 参数。  
  
- 是函数的返回值的记录类型。  
  
  本主题说明如何在 WCF 服务模型中表示的记录类型。 有关如何调用 Oracle 过程和函数的信息，请参阅[调用的函数和使用 WCF 服务模型的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例使用 ACCOUNT_PKG SCOTT/Oracle PL/SQL 包。 下列元素用于从 ACCOUNT_PKG。  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 一个脚本来生成此包提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 有关详细信息，请参阅脚本  
  
 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="record-types-in-the-wcf-service-model"></a>WCF 服务模型中的记录类型  
 Oracle 记录类型表示为复杂的 XML 类型由[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 在 WCF 服务模型中，由一个类，表示 XML 的复杂类型，此类的属性表示 Oracle 记录类型的字段。 表示的记录类型参数的类生成由包 （如果有） 和函数或过程的架构限定的命名空间中。 此命名空间唯一标识的函数或过程的参数。 例如，在以下命名空间中创建 Oracle 包 ACCOUNT_PKG 中的 CREATE_ACCOUNT 过程的记录类型参数： `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`。 有关在 WCF 服务模型中用于表示过程和函数中的复杂类型的命名空间的详细信息，请参阅[调用的函数和使用 WCF 服务模型的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
 时的记录类型参数的命名空间由过程或函数，记录类型参数为生成的类的名称记录类型进行声明的方式确定。 下表显示了如何生成的类的名称基于 Oracle 记录类型参数声明的两种不同方法。  
  
|Oracle 记录类型|“属性”|示例|  
|------------------------|----------|-------------|  
|表 %rowtype 过程或函数参数|[PARAMETER_NAME]RECORD|ACCTRECORD|  
|记录包参数的类型|[PACKAGE_NAME][RECORD_TYPE_NAME]RECORD|ACCOUNT_PKGACCTINFO_REC_TYPERECORD|  
  
 [PARAMETER_NAME] = 的过程或函数参数，则名称例如，帐户  
  
 [PACKAGE_NAME] = Oracle 包的名称。  
  
 [RECORD_TYPE_NAME] = 记录类型声明; 中指定的名称例如，ACCTINFO_REC_TYPE。  
  
 以下代码显示为两个 Oracle 函数生成 WCF 客户端的方法签名。 /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 函数采用两个简单记录类型 IN 参数，并且 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO 函数返回包含两个嵌套的记录类型的记录类型参数。 Oracle 函数声明是包括在代码的顶部。 每个函数的参数是由唯一的命名空间限定。  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 下面的代码显示了为 CREATE_ACCOUNT 函数的参数生成的类： `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`  
  
 此函数已用表 %行类型声明的参数和参数的类型的记录包类型声明 (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT {  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGADDRESS_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
}  
```  
  
### <a name="representation-of-a-simple-record-type"></a>简单记录类型的表示形式  
 下面的代码演示如何在 WCF 服务模型中表示一个简单的记录类型。 此代码显示了已展开的视图**ACCOUNTRECORD**表示 CREATE_ACCOUNT 函数中的帐户 %行类型参数的类。 在此类中记录字段 （行列） 表示为属性。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Runtime.Serialization.DataContractAttribute()]  
public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
    private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
    private System.Nullable<decimal> ACCTIDField;  
  
    private string NAMEField;  
  
    private System.Nullable<decimal> BALANCEField;  
  
    public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
        get {  
            return this.extensionDataField;  
        }  
        set {  
            this.extensionDataField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public System.Nullable<decimal> ACCTID {  
        get {  
            return this.ACCTIDField;  
        }  
        set {  
            this.ACCTIDField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public string NAME {  
        get {  
            return this.NAMEField;  
        }  
        set {  
            this.NAMEField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute(Order=2)]  
    public System.Nullable<decimal> BALANCE {  
        get {  
            return this.BALANCEField;  
        }  
        set {  
            this.BALANCEField = value;  
        }  
    }  
}  
```  
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a>包含嵌套的记录的记录类型的表示形式  
 下面的代码显示了包含嵌套的记录的记录类型的表示形式。 这种特定记录类型是 GET_ACCOUNTINFO 函数的返回值 (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`)。 ACCTINFO_REC_TYPE 为包参数使用一个类型的记录构造声明 (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。 它包含两个嵌套的简单记录类型，表 %行记录和记录类型记录的包。 这两个简单记录在其父记录相同的命名空间中声明，并按照预期的命名约定。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGACCTINFO_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCTField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESSField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCT {  
            get {  
                return this.ACCTField;  
            }  
            set {  
                this.ACCTField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESS {  
            get {  
                return this.ADDRESSField;  
            }  
            set {  
                this.ADDRESSField = value;  
            }  
        }  
    }  
```  
  
## <a name="using-record-types-in-your-code"></a>在你的代码中使用记录类型  
 在代码中使用的记录类型非常简单。 若要调用的过程或函数中的记录类型参数，创建记录类型或类型的实例，并将其传递给适当的方法，WCF 客户端上。 过程或函数返回时，可以读取任何扩展属性或在 OUT 参数或函数返回的值时被声明为记录类型。 有关如何使用 WCF 服务模型调用过程和函数的详细信息，请参阅[调用的函数和使用 WCF 服务模型的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。  
  
> [!IMPORTANT]
>  Oracle 记录类型参数 （和函数返回） 由其函数或过程 （以及包） 的命名空间限定。 这意味着，在两个不同的过程或函数中使用的记录类型将具有不同的命名空间为每个过程或函数。 您必须确保要使用的特定过程或函数时正确限定记录类型。 例如，将使用对应于为每个函数生成的唯一命名空间的每个声明两次在 WCF 客户端代码声明包用作两个不同的函数的 IN 参数的记录类型 （记录的类型声明）。 您必须确保使用正确的命名空间上将传递给每个相应的函数的参数。  
  
 在以下示例中，使用两个简单的记录参数调用 CREATE_ACCOUNT 函数。 接下来，调用 GET_ACCOUNTINFO 函数。 此函数返回包含嵌套的记录的记录类型。 所选的字段中返回的记录的值写入到控制台。 此示例中省略了步骤来设置 Oracle 数据库的凭据，并打开 WCF 客户端。  
  
```  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
…  
  
// Create the client from configuration  
using (SCOTTPackageACCOUNT_PKGClient accountPkgClient = new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG"))  
{  
  
    ...  
  
    decimal acctId;  
  
    // Create an account record  
    // Note: ACCTRECORD is defined in both namespaces so specify the definition  
    // that corresponds to the client.  
  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD acctRec =   
        new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD();  
  
    // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
    acctRec.ACCTID = 0;  
    acctRec.NAME = "Anton Kirilov";  
    acctRec.BALANCE = 9583;  
  
    // Create address record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
    addrRec.STREET = "234 Main St";  
    addrRec.CITY = "Boston";  
    addrRec.STATE = "MA";  
  
    // Create account  
    try  
    {  
        acctId = (decimal)accountPkgClient.CREATE_ACCOUNT(acctRec, addrRec);  
    }  
    catch (Exception ex)  
    {  
        // handle exception  
        ...  
    }  
  
    ...  
  
    // Account info record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD acctInfo =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD();  
  
    // Get account info for the account just created  
    // acctInfo is returned as a nested record type  
    try  
    {  
     acctInfo = accountPkgClient.GET_ACCOUNTINFO(acctId);  
    }  
    catch (Exception ex)  
    {  
    // handle exception  
    ...  
    }  
  
    // Write the account info to the console  
    Console.WriteLine("The account info is:");  
    Console.WriteLine("Name:\t\t\t{0}", acctInfo.ACCT.NAME);  
    Console.WriteLine("Street:\t\t\t{0}", acctInfo.ADDRESS.STREET);  
    Console.WriteLine("City:\t\t\t{0}", acctInfo.ADDRESS.CITY);  
    Console.WriteLine("State:\t\t\t{0}", acctInfo.ADDRESS.STATE);  
    Console.WriteLine("Account Id:\t\t{0}", acctInfo.ACCT.ACCTID);  
    Console.WriteLine("Account Balance:\t{0:C}", acctInfo.ACCT.BALANCE);  
  
    Console.WriteLine("\nHit <RETURN> to finish");  
    Console.ReadLine();  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)