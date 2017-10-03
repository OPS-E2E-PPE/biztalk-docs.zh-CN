---
title: "使用 WCF 服务模型的 Oracle 数据库中运行操作使用 REF CURSOR |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb527a4451388475ce69a5321d0d05616fc8afde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="e0ddd-102">使用 WCF 服务模型的 Oracle 数据库中运行操作使用 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="e0ddd-102">Run Operations Using REF CURSORS in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="e0ddd-103">REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="e0ddd-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]在过程、 函数和包支持 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports REF CURSOR parameters in procedures, functions, and packages.</span></span> <span data-ttu-id="e0ddd-105">REF CURSOR 参数可以是强类型或弱类型具体取决于在过程或函数中的声明。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-105">REF CURSOR parameters can be strongly-typed or weakly-typed depending on how they are declared in the procedure or function.</span></span> <span data-ttu-id="e0ddd-106">有关如何通过表示 REF CURSOR 参数的详细说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[REF CURSOR 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。下表总结了 REF CURSOR 参数 WCF 服务模型中的表示方式。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-106">For a detailed explanation of how REF CURSOR parameters are represented by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for REF CURSORS](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).The following table summarizes how REF CURSOR parameters are represented in the WCF service model.</span></span>  
  
|<span data-ttu-id="e0ddd-107">参数方向</span><span class="sxs-lookup"><span data-stu-id="e0ddd-107">Parameter Direction</span></span>|<span data-ttu-id="e0ddd-108">强类型化的 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="e0ddd-108">Strongly-typed REF CURSOR</span></span>|<span data-ttu-id="e0ddd-109">弱类型化的 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="e0ddd-109">Weakly-typed REF CURSOR</span></span>|  
|-------------------------|--------------------------------|------------------------------|  
|<span data-ttu-id="e0ddd-110">IN</span><span class="sxs-lookup"><span data-stu-id="e0ddd-110">IN</span></span>|`string [PARAM_NAME]`<br /><br /> <span data-ttu-id="e0ddd-111">包含 PL/SQL 块的字符串。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-111">String that contains a PL/SQL block.</span></span> <span data-ttu-id="e0ddd-112">通过执行"打开为 SELECT"语句或通过调用函数或过程，PL/SQL 块必须返回打开的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-112">The PL/SQL block must return an opened REF CURSOR either by executing an "OPEN FOR SELECT" statement or by invoking a function or procedure.</span></span> <span data-ttu-id="e0ddd-113">问号 （？） 指示 REF CURSOR 返回参数的位置。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-113">A question mark (?) indicates the position of the REF CURSOR that returns the parameter.</span></span> <span data-ttu-id="e0ddd-114">例如，"开始打开？</span><span class="sxs-lookup"><span data-stu-id="e0ddd-114">For example, "BEGIN OPEN ?</span></span> <span data-ttu-id="e0ddd-115">为选择 * 从 MY_TABLE;结束"，或"开始 MY_PROC (PARM1，？，PARM2);结束;"。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-115">FOR SELECT * FROM MY_TABLE; END", or "BEGIN MY_PROC(PARM1, ?, PARM2); END;".</span></span>|<span data-ttu-id="e0ddd-116">强类型相同</span><span class="sxs-lookup"><span data-stu-id="e0ddd-116">Same as strongly-typed</span></span>|  
|<span data-ttu-id="e0ddd-117">OUT</span><span class="sxs-lookup"><span data-stu-id="e0ddd-117">OUT</span></span>|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="e0ddd-118">强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-118">A strongly-typed record set.</span></span>|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="e0ddd-119">弱类型泛型记录集。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-119">A weakly-typed generic record set.</span></span>|  
|<span data-ttu-id="e0ddd-120">OUT IN</span><span class="sxs-lookup"><span data-stu-id="e0ddd-120">IN OUT</span></span>|<span data-ttu-id="e0ddd-121">在出 REF CURSOR 参数被拆分为 IN 和 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-121">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="e0ddd-122">在方法签名，以将其从 OUT 参数区分开"_IN"追加 IN 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-122">The IN parameter is appended with "_IN" in the method signature to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="e0ddd-123">OUT 参数表示通过强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-123">The OUT parameter is represented by a strongly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|<span data-ttu-id="e0ddd-124">在出 REF CURSOR 参数被拆分为 IN 和 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-124">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="e0ddd-125">"_IN"区分开来 OUT 参数追加 IN 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-125">The IN parameter is appended with "_IN" to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="e0ddd-126">由弱类型的记录集表示 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-126">The OUT parameter is represented by a weakly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 <span data-ttu-id="e0ddd-127">[PARAM_NAME] = 对 Oracle 数据库; 的函数或过程定义中的参数的名称例如，MYREFCURSOR。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-127">[PARAM_NAME] = the name of the parameter in the function or procedure definition on the Oracle database; for example, MYREFCURSOR.</span></span>  
  
 <span data-ttu-id="e0ddd-128">[PROC_NS] = 生成为包含参数的包、 过程或函数; 唯一的命名空间例如，"microsoft.lobservices.oracledb._2007._03.SCOTT。Package.ACCOUNT_PKG。GET_ACTIVITY"。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-128">[PROC_NS] = The unique namespace generated to contain parameters of the package, procedure, or function; for example, "microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY".</span></span>  
  
 <span data-ttu-id="e0ddd-129">[GENERIC_NS] = 定义泛型的记录集的命名空间"microsoft.lobservices.oracledb._2007._03"。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-129">[GENERIC_NS] = The namespace in which the generic record set is defined, "microsoft.lobservices.oracledb._2007._03".</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e0ddd-130">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="e0ddd-130">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e0ddd-131">本主题中的示例使用 SCOTT/包/ACCOUNT_PKG Oracle 包。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-131">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG Oracle PACKAGE.</span></span> <span data-ttu-id="e0ddd-132">从 ACCOUNT_PKG 使用下列过程：</span><span class="sxs-lookup"><span data-stu-id="e0ddd-132">The following procedure is used from ACCOUNT_PKG:</span></span>  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 <span data-ttu-id="e0ddd-133">使用 SDK 示例提供了一个脚本以生成此包。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-133">A script to generate this package is supplied with the SDK samples.</span></span> <span data-ttu-id="e0ddd-134">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-134">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a><span data-ttu-id="e0ddd-135">WCF 服务模型中的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e0ddd-135">REF CURSOR Parameters in the WCF Service Model</span></span>  
 <span data-ttu-id="e0ddd-136">下面的示例显示的类和 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程生成的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-136">The following examples show the classes and WCF client generated for the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure.</span></span> <span data-ttu-id="e0ddd-137">此过程具有弱类型 IN 出 REF CURSOR 参数以及强类型 IN 出 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-137">This procedure has weakly-typed IN and OUT REF CURSOR parameters and a strongly-typed IN OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="e0ddd-138">下面是方法的在 WCF 客户端以调用 GET_ACTIVITY 中生成的签名。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-138">Here is the signature of the method that is generated in the WCF client to invoke GET_ACTIVITY.</span></span>  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 <span data-ttu-id="e0ddd-139">在**GET_ACTIVITY**方法，在 OUT 参数 INOUTRECS 拆分为两个参数：</span><span class="sxs-lookup"><span data-stu-id="e0ddd-139">In the **GET_ACTIVITY** method, the IN OUT parameter INOUTRECS is split into two parameters:</span></span>  
  
-   <span data-ttu-id="e0ddd-140">INOUTRECS_IN 是一个字符串，表示在 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-140">INOUTRECS_IN is a string that represents an IN REF CURSOR parameter.</span></span>  
  
-   <span data-ttu-id="e0ddd-141">INOUTRECS 是一个表示出 REF CURSOR 参数的强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-141">INOUTRECS is a strongly-typed record set that represents an OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="e0ddd-142">弱类型 OUT 参数，OUTRECS，表示为泛型的记录集。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-142">The weakly-typed OUT parameter, OUTRECS, is represented as a generic record set.</span></span> <span data-ttu-id="e0ddd-143">弱类型参数，INRECS 中, 都表示为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-143">The weakly-typed IN parameter, INRECS, is represented as a string.</span></span>  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="e0ddd-144">强类型出 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e0ddd-144">Strongly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="e0ddd-145">强类型扩展 （或在缩小） 中一个基于架构、 包和过程或函数在其中使用它们的名称的唯一命名空间中生成的 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-145">Strongly-typed OUT (or IN OUT) REF CURSOR parameters are generated in a unique namespace based on the SCHEMA, PACKAGE, and name of the procedure or function in which they are used.</span></span> <span data-ttu-id="e0ddd-146">对于 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程中，此命名空间是`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-146">For the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure, this namespace is `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span></span> <span data-ttu-id="e0ddd-147">由"记录"的参数的名称构成的类名称和类组成表示 Oracle 字段的属性。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-147">The class name is formed by appending the name of the parameter with "RECORD" and the class is composed of properties that represent the Oracle fields.</span></span> <span data-ttu-id="e0ddd-148">下图显示表示为 INOUTRECS REF CURSOR 参数生成的强类型的记录的类的一部分。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-148">The following shows a part of the class that represents the strongly-typed records generated for the INOUTRECS REF CURSOR parameter.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class INOUTRECSRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private System.Nullable<decimal> TIDField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public System.Nullable<decimal> TID {  
            get {  
                return this.TIDField;  
            }  
            set {  
                this.TIDField = value;  
            }  
        }  
  
        ...  
  
    }  
}  
```  
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="e0ddd-149">弱类型出 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e0ddd-149">Weakly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="e0ddd-150">弱类型扩展 （或在缩小） REF CURSOR 参数表示通过通用记录类。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-150">Weakly-typed OUT (or IN OUT) REF CURSOR parameters are represented by the generic record class.</span></span> <span data-ttu-id="e0ddd-151">泛型的记录集将始终生成相同的命名空间，并且具有相同的类名称，而不考虑函数或过程。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-151">The generic record set is always generated in the same namespace and with the same class name regardless of the function or procedure.</span></span> <span data-ttu-id="e0ddd-152">下面的代码演示通用记录类， **microsoft.lobservices.oracledb._2007._03.GenRecordRow**，它表示 OUTRECS 出 SYS_REFCURSOR 参数 （弱类型） 的记录。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-152">The following code shows the generic record class, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, which represents the records for the OUTRECS OUT SYS_REFCURSOR parameter (weakly-typed).</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordRow : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumnField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumn {  
            get {  
                return this.GenRecordColumnField;  
            }  
            set {  
                this.GenRecordColumnField = value;  
            }  
        }  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordColumn : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private string ColumnNameField;  
  
        private string ColumnValueField;  
  
        private string ColumnTypeField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false)]  
        public string ColumnName {  
            get {  
                return this.ColumnNameField;  
            }  
            set {  
                this.ColumnNameField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public string ColumnValue {  
            get {  
                return this.ColumnValueField;  
            }  
            set {  
                this.ColumnValueField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false, Order=2)]  
        public string ColumnType {  
            get {  
                return this.ColumnTypeField;  
            }  
            set {  
                this.ColumnTypeField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a><span data-ttu-id="e0ddd-153">使用 WCF 客户端的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e0ddd-153">Using REF CURSOR Parameters with a WCF Client</span></span>  
 <span data-ttu-id="e0ddd-154">若要通过使用 WCF 客户端调用过程或函数的 REF CURSOR 参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0ddd-154">To invoke a procedure or function with REF CURSOR parameters by using a WCF client, you do the following:</span></span>  
  
1.  <span data-ttu-id="e0ddd-155">将字符串传递中的 for each 或 IN 出 REF CURSOR 参数，其中包含 PL/SQL 阻止打开 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-155">Pass a string for each IN or IN OUT REF CURSOR parameter that contains the PL/SQL block to open the REF CURSOR.</span></span> <span data-ttu-id="e0ddd-156">此块可以执行一个打开的 SELECT 语句，或调用的函数或 OUT 参数中返回打开的 REF CURSOR 的过程。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-156">This block can either execute an OPEN FOR SELECT statement or invoke a function or procedure that returns an opened REF CURSOR in an OUT parameter.</span></span>  
  
2.  <span data-ttu-id="e0ddd-157">在过程或函数返回时，操作中返回的任何 OUT 或 IN 出 REF CURSOR 参数的记录集的数据。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-157">When the procedure or function returns, operate on the data in the record sets returned for any OUT or IN OUT REF CURSOR parameters.</span></span> <span data-ttu-id="e0ddd-158">记录集将是通用记录为弱类型 REF CURSOR 参数设置或为强类型化的 REF CURSOR 参数设置的强类型的记录。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-158">The record set will be a generic record set for weakly-typed REF CURSOR parameters or a strongly-typed record set for strongly-typed REF CURSOR parameters.</span></span>  
  
 <span data-ttu-id="e0ddd-159">有关如何使用 WCF 服务模型调用过程和函数的详细信息，请参阅[调用函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-159">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="e0ddd-160">下面的示例调用 GET_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-160">The following example calls the GET_ACTIVITY procedure.</span></span> <span data-ttu-id="e0ddd-161">它演示了这两个指定 IN REF CURSOR 参数的方法：</span><span class="sxs-lookup"><span data-stu-id="e0ddd-161">It demonstrates both ways of specifying an IN REF CURSOR parameter:</span></span>  
  
-   <span data-ttu-id="e0ddd-162">对于在 REF CURSOR 参数，一个打开的 SELECT 语句指定要为帐户 100001 返回活动。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-162">For the IN REF CURSOR parameter, an OPEN FOR SELECT statement is specified to return activity for ACCOUNT 100001.</span></span>  
  
-   <span data-ttu-id="e0ddd-163">对于在出 REF CURSOR 参数，将调用 /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-163">For the IN OUT REF CURSOR parameter, the /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY procedure is invoked.</span></span> <span data-ttu-id="e0ddd-164">此过程将打开包含所有 ACCOUNTACTIVITY 表中的活动并将其作为 OUT 参数返回 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-164">This procedure opens a REF CURSOR that contains all of the activity in the ACCOUNTACTIVITY table and returns it as an OUT parameter.</span></span>  
  
 <span data-ttu-id="e0ddd-165">该示例还演示如何读取从记录集的强类型和弱类型都 REF CURSOR 参数返回的数据。</span><span class="sxs-lookup"><span data-stu-id="e0ddd-165">The example also demonstrates how to read data from the record set returned for both strongly-typed and weakly-typed REF CURSOR parameters.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// namespaces for strongly-typed and weakly typed REF CURSOR records  
using GET_ACTIVITYns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY;  
using GENERICns = microsoft.lobservices.oracledb._2007._03;  
  
// In this sample, INRECS is opened by using an OPEN FOR statement, and  
// INOUTRECS_IN is opened by calling the GET_ALL_ACTIVITY procedure on Oracle.  
  
namespace OracleRefCursorsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the client  
            SCOTTPackageACCOUNT_PKGClient accountPkgClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // Set credentials  
            accountPkgClient.ClientCredentials.UserName.UserName = "SCOTT";  
            accountPkgClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
  
                GET_ACTIVITYns.INOUTRECSRECORD[] strongCursor;  
                GENERICns.GenRecordRow[] weakCursor;  
  
                Console.WriteLine("Opening client");  
                // Open the client  
                accountPkgClient.Open();  
  
                Console.WriteLine("Invoking ACCOUNT_PKG.GET_ACTIVITY");  
                // Get  ACCOUNTACTIVITY records  
                // The IN REF CURSOR is set to all activity for account 100001  
                // The input part of the IN OUT ref cursor calls GET_ALL_ACTIVITY  
                // The weakly-typed OUT REF CURSOR parameter returns a list of activity for account 100001  
                // The strongly-typed IN OUT REF CURSOR parameter returns a list of all activity  
                string inRecsString = "BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;";  
                string inoutRecsString = "BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;";  
  
                accountPkgClient.GET_ACTIVITY(  
                                inRecsString,  
                                inoutRecsString,  
                                out strongCursor,  
                                out weakCursor);  
  
                // Display strong ref cursor (all activity)  
                Console.WriteLine("\nList of all activity returned (strong ref cursor)");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < strongCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2:C}\t{3}\t{4}",strongCursor[i].TID,  
                        strongCursor[i].ACCOUNT,   
                        strongCursor[i].AMOUNT,   
                        strongCursor[1].TRANSDATE,  
                        strongCursor[i].DESCRIPTION);  
                }  
  
                // Display weak ref cursor (account 100001)  
                Console.WriteLine("\nList of activity for account 100001 returned (weak ref cursor)");  
                Console.WriteLine("Tx Id\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < weakCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1:C}\t{2}\t{3}", weakCursor[i].GenRecordColumn[0].ColumnValue,  
                        weakCursor[i].GenRecordColumn[2].ColumnValue,  
                        weakCursor[i].GenRecordColumn[4].ColumnValue,  
                        weakCursor[i].GenRecordColumn[3].ColumnValue);  
                }  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
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
                // Close the client  
                accountPkgClient.Close();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0ddd-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ddd-166">See Also</span></span>  
 [<span data-ttu-id="e0ddd-167">开发使用 WCF 服务模型的 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="e0ddd-167">Develop Oracle Database Application Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)