---
title: "使用 WCF 服务模型的 Oracle 数据库中运行操作使用的记录类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3de78290e29c4c1ddc1465e8a9463a6e9d7b86f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="6ad78-102">使用 WCF 服务模型的 Oracle 数据库中运行操作使用的记录类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-102">Run Operations Using RECORD Types in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="6ad78-103">Oracle 记录类型用于表示传递给 PL/SQL 函数和过程的参数中的分层信息。</span><span class="sxs-lookup"><span data-stu-id="6ad78-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="6ad78-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为复杂的 XML 类型的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="6ad78-105">在 WCF 服务模型中，记录类型反序列化到强类型化.NET 类。</span><span class="sxs-lookup"><span data-stu-id="6ad78-105">In the WCF service model, RECORD types are deserialized to strongly-typed .NET classes.</span></span> <span data-ttu-id="6ad78-106">记录字段表示为类的属性。</span><span class="sxs-lookup"><span data-stu-id="6ad78-106">The record fields are represented as properties on the class.</span></span>  
  
 <span data-ttu-id="6ad78-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持以下类型的记录类型：</span><span class="sxs-lookup"><span data-stu-id="6ad78-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
-   <span data-ttu-id="6ad78-108">声明为表中存储的过程和函数的 %rowtype 参数的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-108">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="6ad78-109">例如，声明为类型的记录参数 PL/SQL 包中的记录类型`TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span><span class="sxs-lookup"><span data-stu-id="6ad78-109">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span></span>  
  
-   <span data-ttu-id="6ad78-110">包含嵌套的记录的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-110">RECORD types that contain nested records.</span></span>  
  
-   <span data-ttu-id="6ad78-111">记录中显示类型，作为，出或在 OUT 参数为过程或函数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
-   <span data-ttu-id="6ad78-112">是函数的返回值的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-112">RECORD types that are RETURN values of functions.</span></span>  
  
 <span data-ttu-id="6ad78-113">本主题说明如何在 WCF 服务模型中表示记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-113">This topic shows how RECORD types are represented in the WCF service model.</span></span> <span data-ttu-id="6ad78-114">有关如何调用 Oracle 过程和函数的信息，请参阅[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-114">For information about how to call Oracle procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="6ad78-115">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="6ad78-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="6ad78-116">本主题中的示例使用 SCOTT/ACCOUNT_PKG Oracle PL/SQL 包。</span><span class="sxs-lookup"><span data-stu-id="6ad78-116">The examples in this topic use the /SCOTT/ACCOUNT_PKG Oracle PL/SQL PACKAGE.</span></span> <span data-ttu-id="6ad78-117">从 ACCOUNT_PKG，使用以下元素。</span><span class="sxs-lookup"><span data-stu-id="6ad78-117">The following elements are used from ACCOUNT_PKG.</span></span>  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 <span data-ttu-id="6ad78-118">用于生成此包的脚本提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="6ad78-118">A script to generate this package is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="6ad78-119">有关详细信息，请参阅脚本</span><span class="sxs-lookup"><span data-stu-id="6ad78-119">For more information, see the script</span></span>  
  
 <span data-ttu-id="6ad78-120">有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-120">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="record-types-in-the-wcf-service-model"></a><span data-ttu-id="6ad78-121">WCF 服务模型中的记录类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-121">RECORD Types in the WCF Service Model</span></span>  
 <span data-ttu-id="6ad78-122">Oracle 记录类型表示为复杂的 XML 类型，通过[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6ad78-122">Oracle RECORD types are represented as complex XML types by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="6ad78-123">在 WCF 服务模型中，由一个类，表示复杂的 XML 类型和此类的属性表示 Oracle 记录类型的字段。</span><span class="sxs-lookup"><span data-stu-id="6ad78-123">In the WCF service model, complex XML types are represented by a class, and the properties of this class represent the fields of the Oracle RECORD type.</span></span> <span data-ttu-id="6ad78-124">表示一个记录类型参数的类将由包 （如果有） 和函数或过程的架构限定的命名空间中生成。</span><span class="sxs-lookup"><span data-stu-id="6ad78-124">The class that represents a RECORD type parameter is generated in a namespace that is qualified by the PACKAGE (if any) and SCHEMA of the function or procedure.</span></span> <span data-ttu-id="6ad78-125">此命名空间唯一标识的函数或过程的参数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-125">This namespace uniquely identifies the function or procedure of the parameter.</span></span> <span data-ttu-id="6ad78-126">例如，在以下命名空间中创建 Oracle 包 ACCOUNT_PKG 中的 CREATE_ACCOUNT 过程的记录类型参数： `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`。</span><span class="sxs-lookup"><span data-stu-id="6ad78-126">For example, the RECORD type parameters to the CREATE_ACCOUNT procedure in the Oracle PACKAGE ACCOUNT_PKG are created in the following namespace: `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`.</span></span> <span data-ttu-id="6ad78-127">有关在 WCF 服务模型中用于表示过程或函数中的复杂类型的命名空间的详细信息，请参阅[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-127">For more information about the namespaces used in the WCF service model to represent complex types in procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="6ad78-128">时记录类型参数的命名空间由过程或函数，则会在其中声明记录类型顺便说一下确定的记录类型参数为生成的类名。</span><span class="sxs-lookup"><span data-stu-id="6ad78-128">While the namespace of a RECORD type parameter is determined by the procedure or function, the name of the class generated for the RECORD type parameter is determined by the way in which the RECORD type is declared.</span></span> <span data-ttu-id="6ad78-129">下表演示了如何生成的类名称基于声明的 Oracle 记录类型参数的两种不同方法。</span><span class="sxs-lookup"><span data-stu-id="6ad78-129">The following table shows how the name of the class is generated based on the two different ways of declaring the Oracle RECORD type parameter.</span></span>  
  
|<span data-ttu-id="6ad78-130">Oracle 记录类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-130">Oracle RECORD type</span></span>|<span data-ttu-id="6ad78-131">Name</span><span class="sxs-lookup"><span data-stu-id="6ad78-131">Name</span></span>|<span data-ttu-id="6ad78-132">示例</span><span class="sxs-lookup"><span data-stu-id="6ad78-132">Example</span></span>|  
|------------------------|----------|-------------|  
|<span data-ttu-id="6ad78-133">表 %rowtype 过程或函数参数</span><span class="sxs-lookup"><span data-stu-id="6ad78-133">TABLE%ROWTYPE procedure or function parameter</span></span>|<span data-ttu-id="6ad78-134">[PARAMETER_NAME]记录</span><span class="sxs-lookup"><span data-stu-id="6ad78-134">[PARAMETER_NAME]RECORD</span></span>|<span data-ttu-id="6ad78-135">ACCTRECORD</span><span class="sxs-lookup"><span data-stu-id="6ad78-135">ACCTRECORD</span></span>|  
|<span data-ttu-id="6ad78-136">记录包参数的类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-136">TYPE of RECORD package parameter</span></span>|<span data-ttu-id="6ad78-137">[PACKAGE_NAME][RECORD_TYPE_NAME]记录</span><span class="sxs-lookup"><span data-stu-id="6ad78-137">[PACKAGE_NAME][RECORD_TYPE_NAME]RECORD</span></span>|<span data-ttu-id="6ad78-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span><span class="sxs-lookup"><span data-stu-id="6ad78-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span></span>|  
  
 <span data-ttu-id="6ad78-139">[PARAMETER_NAME] = 过程或函数的参数; 的名称例如，帐户</span><span class="sxs-lookup"><span data-stu-id="6ad78-139">[PARAMETER_NAME] = the name of the procedure or function parameter; for example, ACCT.</span></span>  
  
 <span data-ttu-id="6ad78-140">[PACKAGE_NAME] = Oracle 包的名称。</span><span class="sxs-lookup"><span data-stu-id="6ad78-140">[PACKAGE_NAME] = the name of the Oracle package.</span></span>  
  
 <span data-ttu-id="6ad78-141">[RECORD_TYPE_NAME] = 记录类型声明中; 中指定的名称例如，ACCTINFO_REC_TYPE。</span><span class="sxs-lookup"><span data-stu-id="6ad78-141">[RECORD_TYPE_NAME] = the name specified in the RECORD TYPE declaration; for example, ACCTINFO_REC_TYPE.</span></span>  
  
 <span data-ttu-id="6ad78-142">下面的代码演示对两个 Oracle 函数生成 WCF 客户端的方法签名。</span><span class="sxs-lookup"><span data-stu-id="6ad78-142">The following code shows the method signatures of the WCF client generated for two Oracle functions.</span></span> <span data-ttu-id="6ad78-143">/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT 函数采用两个简单记录类型 IN 参数，并 /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO 函数返回包含两个嵌套的记录类型的记录类型参数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-143">The /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT function takes two simple RECORD type IN parameters, and the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO function returns a RECORD type parameter that contains two nested RECORD types.</span></span> <span data-ttu-id="6ad78-144">Oracle 函数声明不包括在代码的顶部。</span><span class="sxs-lookup"><span data-stu-id="6ad78-144">The Oracle function declarations are included at the top of the code.</span></span> <span data-ttu-id="6ad78-145">每个函数的参数是由唯一的命名空间限定。</span><span class="sxs-lookup"><span data-stu-id="6ad78-145">The parameters of each function are qualified by a unique namespace.</span></span>  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 <span data-ttu-id="6ad78-146">下面的代码演示生成的参数的 CREATE_ACCOUNT 函数的类：`FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span><span class="sxs-lookup"><span data-stu-id="6ad78-146">The following code shows the classes generated for the parameters of the CREATE_ACCOUNT function: `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span></span>  
  
 <span data-ttu-id="6ad78-147">此函数具有与表 %rowtype 声明的参数和声明与某个类型的记录包类型的参数 (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-147">This function has a parameter declared with a TABLE%ROWTYPE and a parameter declared with a TYPE of RECORD package type (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span>  
  
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
  
### <a name="representation-of-a-simple-record-type"></a><span data-ttu-id="6ad78-148">简单的记录类型的表示形式</span><span class="sxs-lookup"><span data-stu-id="6ad78-148">Representation of a Simple Record Type</span></span>  
 <span data-ttu-id="6ad78-149">下面的代码演示如何在 WCF 服务模型中表示简单的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-149">The following code shows how a simple RECORD type is represented in the WCF service model.</span></span> <span data-ttu-id="6ad78-150">此代码演示的已展开的视图**ACCOUNTRECORD**表示 CREATE_ACCOUNT 函数中的帐户 %rowtype 参数的类。</span><span class="sxs-lookup"><span data-stu-id="6ad78-150">This code shows the expanded view of the **ACCOUNTRECORD** class that represents the ACCOUNT%ROWTYPE parameter in the CREATE_ACCOUNT function.</span></span> <span data-ttu-id="6ad78-151">在此类中的记录字段 （行列） 表示为属性。</span><span class="sxs-lookup"><span data-stu-id="6ad78-151">In this class, the record fields (row columns) are represented as properties.</span></span>  
  
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
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a><span data-ttu-id="6ad78-152">表示形式包含嵌套的记录的记录类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-152">Representation of a Record Type that Contains Nested Records</span></span>  
 <span data-ttu-id="6ad78-153">下面的代码演示的表示形式包含嵌套的记录的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-153">The following code shows the representation of a RECORD type that contains nested records.</span></span> <span data-ttu-id="6ad78-154">此特定记录类型是 GET_ACCOUNTINFO 函数的返回值 (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-154">This particular RECORD type is the RETURN value of the GET_ACCOUNTINFO function (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`).</span></span> <span data-ttu-id="6ad78-155">ACCTINFO_REC_TYPE 为包参数使用一个类型的记录构造声明 (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-155">The ACCTINFO_REC_TYPE is a package parameter declared using a TYPE of RECORD construct (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span> <span data-ttu-id="6ad78-156">它包含两个嵌套的简单记录类型，表 %行记录和包类型的记录。</span><span class="sxs-lookup"><span data-stu-id="6ad78-156">It contains two nested simple record types, a TABLE%ROW record and a package TYPE of RECORD record.</span></span> <span data-ttu-id="6ad78-157">这两个简单记录在其父记录相同的命名空间中声明，并按照预期的命名约定。</span><span class="sxs-lookup"><span data-stu-id="6ad78-157">These two simple records are declared in the same namespace as their parent record and follow the expected naming convention.</span></span>  
  
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
  
## <a name="using-record-types-in-your-code"></a><span data-ttu-id="6ad78-158">使用你代码中的记录类型</span><span class="sxs-lookup"><span data-stu-id="6ad78-158">Using RECORD Types in Your Code</span></span>  
 <span data-ttu-id="6ad78-159">在代码中使用记录类型非常简单。</span><span class="sxs-lookup"><span data-stu-id="6ad78-159">Using RECORD types in your code is straightforward.</span></span> <span data-ttu-id="6ad78-160">若要调用的过程或记录类型参数的函数，创建记录类型或类型的实例，并将其传递给相应的方法，而 WCF 客户端上。</span><span class="sxs-lookup"><span data-stu-id="6ad78-160">To invoke a procedure or function with a RECORD type parameter, you create an instance of the RECORD type or types and pass it to the appropriate method on the WCF client.</span></span> <span data-ttu-id="6ad78-161">过程或函数返回时，你可以读取在任何出的属性或在 OUT 参数或函数返回值时被声明为记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-161">When the procedure or function returns, you can read properties on any OUT or IN OUT parameters or function RETURN values that are declared as RECORD types.</span></span> <span data-ttu-id="6ad78-162">有关如何使用 WCF 服务模型调用过程和函数的详细信息，请参阅[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6ad78-162">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ad78-163">Oracle 记录类型参数 （和函数返回） 及其的函数或过程 （和包） 的命名空间限定。</span><span class="sxs-lookup"><span data-stu-id="6ad78-163">Oracle RECORD type parameters (and function returns) are qualified by the namespace of their function or procedure (and package).</span></span> <span data-ttu-id="6ad78-164">这意味着，在两个不同的过程或函数中使用的记录类型将具有不同的命名空间为每个过程或函数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-164">This means that a RECORD type that is used in two different procedures or functions will have a different namespace for each procedure or function.</span></span> <span data-ttu-id="6ad78-165">你必须确保在使用特定的过程或函数时正确限定记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-165">You must be sure to qualify the RECORD type correctly when you use it for a specific procedure or function.</span></span> <span data-ttu-id="6ad78-166">例如，将对应于为每个函数生成的唯一命名空间的每个声明两次在 WCF 客户端代码声明包作为 IN 参数的两个不同的函数使用的记录类型 （记录的类型声明）。</span><span class="sxs-lookup"><span data-stu-id="6ad78-166">For example, a package RECORD type (RECORD of TYPE declaration) that is used as an IN parameter to two different functions will be declared twice in the WCF client code with each declaration corresponding to the unique namespace generated for each function.</span></span> <span data-ttu-id="6ad78-167">你必须确保将传递给每个相应的函数参数上使用正确的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6ad78-167">You must be sure to use the correct namespace on the parameter that you pass to each respective function.</span></span>  
  
 <span data-ttu-id="6ad78-168">在下面的示例中，使用两个简单的记录参数调用 CREATE_ACCOUNT 函数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-168">In the following example, the CREATE_ACCOUNT function is called with two simple record parameters.</span></span> <span data-ttu-id="6ad78-169">接下来，调用 GET_ACCOUNTINFO 函数。</span><span class="sxs-lookup"><span data-stu-id="6ad78-169">Next, the GET_ACCOUNTINFO function is called.</span></span> <span data-ttu-id="6ad78-170">此函数返回包含嵌套的记录的记录类型。</span><span class="sxs-lookup"><span data-stu-id="6ad78-170">This function returns a RECORD type that contains nested records.</span></span> <span data-ttu-id="6ad78-171">选择的字段中返回的记录的值写入控制台。</span><span class="sxs-lookup"><span data-stu-id="6ad78-171">Selected field values from the returned RECORD are written to the console.</span></span> <span data-ttu-id="6ad78-172">此示例中省略步骤来设置用于 Oracle 数据库的凭据，并打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="6ad78-172">Steps to set credentials for the Oracle database and to open the WCF client are omitted from this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ad78-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ad78-173">See Also</span></span>  
 [<span data-ttu-id="6ad78-174">开发使用 WCF 服务模型的 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="6ad78-174">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)