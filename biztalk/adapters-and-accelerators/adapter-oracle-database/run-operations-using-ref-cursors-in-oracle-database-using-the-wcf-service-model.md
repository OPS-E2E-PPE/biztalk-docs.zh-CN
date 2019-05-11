---
title: 使用 WCF 服务模型的 Oracle 数据库中运行的操作使用 REF CURSOR |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c4d4f9eeac5ebc6b821638f1b1da8276ba4822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376079"
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="abe01-102">使用 WCF 服务模型的 Oracle 数据库中运行的操作使用 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="abe01-102">Run Operations Using REF CURSORS in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="abe01-103">REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。</span><span class="sxs-lookup"><span data-stu-id="abe01-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="abe01-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持 REF CURSOR 参数在过程、 函数和包。</span><span class="sxs-lookup"><span data-stu-id="abe01-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports REF CURSOR parameters in procedures, functions, and packages.</span></span> <span data-ttu-id="abe01-105">REF CURSOR 参数可以是强类型化或弱类型具体取决于在过程或函数中的声明。</span><span class="sxs-lookup"><span data-stu-id="abe01-105">REF CURSOR parameters can be strongly-typed or weakly-typed depending on how they are declared in the procedure or function.</span></span> <span data-ttu-id="abe01-106">有关如何通过表示 REF CURSOR 参数的详细说明[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[REF CURSORS 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)。下表总结了如何在 WCF 服务模型中表示 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-106">For a detailed explanation of how REF CURSOR parameters are represented by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for REF CURSORS](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).The following table summarizes how REF CURSOR parameters are represented in the WCF service model.</span></span>  
  
|<span data-ttu-id="abe01-107">参数方向</span><span class="sxs-lookup"><span data-stu-id="abe01-107">Parameter Direction</span></span>|<span data-ttu-id="abe01-108">强类型化的 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="abe01-108">Strongly-typed REF CURSOR</span></span>|<span data-ttu-id="abe01-109">弱类型化的 REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="abe01-109">Weakly-typed REF CURSOR</span></span>|  
|-------------------------|--------------------------------|------------------------------|  
|<span data-ttu-id="abe01-110">IN</span><span class="sxs-lookup"><span data-stu-id="abe01-110">IN</span></span>|`string [PARAM_NAME]`<br /><br /> <span data-ttu-id="abe01-111">包含一个 PL/SQL 块的字符串。</span><span class="sxs-lookup"><span data-stu-id="abe01-111">String that contains a PL/SQL block.</span></span> <span data-ttu-id="abe01-112">PL/SQL 块必须返回打开的 REF CURSOR，通过执行"打开为 SELECT"语句或调用函数或过程。</span><span class="sxs-lookup"><span data-stu-id="abe01-112">The PL/SQL block must return an opened REF CURSOR either by executing an "OPEN FOR SELECT" statement or by invoking a function or procedure.</span></span> <span data-ttu-id="abe01-113">问号 （？） 指示返回参数的 REF CURSOR 的位置。</span><span class="sxs-lookup"><span data-stu-id="abe01-113">A question mark (?) indicates the position of the REF CURSOR that returns the parameter.</span></span> <span data-ttu-id="abe01-114">例如，"开始打开？</span><span class="sxs-lookup"><span data-stu-id="abe01-114">For example, "BEGIN OPEN ?</span></span> <span data-ttu-id="abe01-115">为选择 \* 从 MY_TABLE;END"，或"开始 MY_PROC (PARM1，？，PARM2);结束;"。</span><span class="sxs-lookup"><span data-stu-id="abe01-115">FOR SELECT \* FROM MY_TABLE; END", or "BEGIN MY_PROC(PARM1, ?, PARM2); END;".</span></span>|<span data-ttu-id="abe01-116">与强类型相同</span><span class="sxs-lookup"><span data-stu-id="abe01-116">Same as strongly-typed</span></span>|  
|<span data-ttu-id="abe01-117">OUT</span><span class="sxs-lookup"><span data-stu-id="abe01-117">OUT</span></span>|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="abe01-118">强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-118">A strongly-typed record set.</span></span>|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="abe01-119">弱类型泛型记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-119">A weakly-typed generic record set.</span></span>|  
|<span data-ttu-id="abe01-120">在 OUT</span><span class="sxs-lookup"><span data-stu-id="abe01-120">IN OUT</span></span>|<span data-ttu-id="abe01-121">在 OUT REF CURSOR 参数被拆分为 IN 和 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-121">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="abe01-122">IN 参数追加在方法签名，以使其不同于 OUT 参数中的"_IN"。</span><span class="sxs-lookup"><span data-stu-id="abe01-122">The IN parameter is appended with "_IN" in the method signature to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="abe01-123">OUT 参数为由强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-123">The OUT parameter is represented by a strongly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|<span data-ttu-id="abe01-124">在 OUT REF CURSOR 参数被拆分为 IN 和 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-124">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="abe01-125">IN 参数后追加"_IN"以便进行区分的 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-125">The IN parameter is appended with "_IN" to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="abe01-126">OUT 参数被表示弱类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-126">The OUT parameter is represented by a weakly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 <span data-ttu-id="abe01-127">[PARAM_NAME] = 对 Oracle 数据库; 在函数或过程定义中参数的名称例如，MYREFCURSOR。</span><span class="sxs-lookup"><span data-stu-id="abe01-127">[PARAM_NAME] = the name of the parameter in the function or procedure definition on the Oracle database; for example, MYREFCURSOR.</span></span>  
  
 <span data-ttu-id="abe01-128">[PROC_NS] = 为包含参数的包、 过程或函数; 而生成的唯一命名空间例如，"microsoft.lobservices.oracledb._2007._03.SCOTT。Package.ACCOUNT_PKG。GET_ACTIVITY"。</span><span class="sxs-lookup"><span data-stu-id="abe01-128">[PROC_NS] = The unique namespace generated to contain parameters of the package, procedure, or function; for example, "microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY".</span></span>  
  
 <span data-ttu-id="abe01-129">[GENERIC_NS] = 在其中定义该泛型的记录集，该命名空间"microsoft.lobservices.oracledb._2007._03"。</span><span class="sxs-lookup"><span data-stu-id="abe01-129">[GENERIC_NS] = The namespace in which the generic record set is defined, "microsoft.lobservices.oracledb._2007._03".</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="abe01-130">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="abe01-130">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="abe01-131">本主题中的示例使用 SCOTT/包/ACCOUNT_PKG Oracle 包。</span><span class="sxs-lookup"><span data-stu-id="abe01-131">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG Oracle PACKAGE.</span></span> <span data-ttu-id="abe01-132">从 ACCOUNT_PKG 使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="abe01-132">The following procedure is used from ACCOUNT_PKG:</span></span>  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 <span data-ttu-id="abe01-133">使用 SDK 示例提供了一个脚本来生成此包。</span><span class="sxs-lookup"><span data-stu-id="abe01-133">A script to generate this package is supplied with the SDK samples.</span></span> <span data-ttu-id="abe01-134">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="abe01-134">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a><span data-ttu-id="abe01-135">在 WCF 服务模型中的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="abe01-135">REF CURSOR Parameters in the WCF Service Model</span></span>  
 <span data-ttu-id="abe01-136">以下示例演示类和 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程生成的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="abe01-136">The following examples show the classes and WCF client generated for the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure.</span></span> <span data-ttu-id="abe01-137">此过程具有弱类型 IN 和 OUT REF CURSOR 参数，强类型化 IN 出 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-137">This procedure has weakly-typed IN and OUT REF CURSOR parameters and a strongly-typed IN OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="abe01-138">以下是方法的在 WCF 客户端以调用 GET_ACTIVITY 中生成的签名。</span><span class="sxs-lookup"><span data-stu-id="abe01-138">Here is the signature of the method that is generated in the WCF client to invoke GET_ACTIVITY.</span></span>  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 <span data-ttu-id="abe01-139">在中**GET_ACTIVITY**方法，在 OUT 参数 INOUTRECS 拆分为两个参数：</span><span class="sxs-lookup"><span data-stu-id="abe01-139">In the **GET_ACTIVITY** method, the IN OUT parameter INOUTRECS is split into two parameters:</span></span>  
  
- <span data-ttu-id="abe01-140">INOUTRECS_IN 是一个字符串，表示在 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-140">INOUTRECS_IN is a string that represents an IN REF CURSOR parameter.</span></span>  
  
- <span data-ttu-id="abe01-141">INOUTRECS 是表示一个 OUT REF CURSOR 参数，强类型化记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-141">INOUTRECS is a strongly-typed record set that represents an OUT REF CURSOR parameter.</span></span>  
  
  <span data-ttu-id="abe01-142">弱类型化 OUT 参数，OUTRECS，表示为泛型的记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-142">The weakly-typed OUT parameter, OUTRECS, is represented as a generic record set.</span></span> <span data-ttu-id="abe01-143">弱类型参数，INRECS 中, 表示为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="abe01-143">The weakly-typed IN parameter, INRECS, is represented as a string.</span></span>  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="abe01-144">强类型扩展的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="abe01-144">Strongly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="abe01-145">强类型化扩展 （或在缩减） 在基于架构、 包和过程或函数使用它们的名称的唯一命名空间中生成 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="abe01-145">Strongly-typed OUT (or IN OUT) REF CURSOR parameters are generated in a unique namespace based on the SCHEMA, PACKAGE, and name of the procedure or function in which they are used.</span></span> <span data-ttu-id="abe01-146">有关 /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY 过程中，此命名空间是`microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`。</span><span class="sxs-lookup"><span data-stu-id="abe01-146">For the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure, this namespace is `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span></span> <span data-ttu-id="abe01-147">由具有"记录"的参数名称构成的类名和类组成表示 Oracle 字段的属性。</span><span class="sxs-lookup"><span data-stu-id="abe01-147">The class name is formed by appending the name of the parameter with "RECORD" and the class is composed of properties that represent the Oracle fields.</span></span> <span data-ttu-id="abe01-148">下面显示了表示 INOUTRECS REF CURSOR 参数生成的强类型记录的类的一部分。</span><span class="sxs-lookup"><span data-stu-id="abe01-148">The following shows a part of the class that represents the strongly-typed records generated for the INOUTRECS REF CURSOR parameter.</span></span>  
  
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
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="abe01-149">弱类型扩展的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="abe01-149">Weakly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="abe01-150">弱类型扩展 （或在缩减） REF CURSOR 参数表示通过通用记录类。</span><span class="sxs-lookup"><span data-stu-id="abe01-150">Weakly-typed OUT (or IN OUT) REF CURSOR parameters are represented by the generic record class.</span></span> <span data-ttu-id="abe01-151">泛型的记录集始终生成相同的命名空间，并且具有相同的类名，而不考虑函数或过程。</span><span class="sxs-lookup"><span data-stu-id="abe01-151">The generic record set is always generated in the same namespace and with the same class name regardless of the function or procedure.</span></span> <span data-ttu-id="abe01-152">下面的代码演示通用记录类**microsoft.lobservices.oracledb._2007._03.GenRecordRow**，它表示 OUTRECS 出 SYS_REFCURSOR 参数 （弱类型化） 的记录。</span><span class="sxs-lookup"><span data-stu-id="abe01-152">The following code shows the generic record class, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, which represents the records for the OUTRECS OUT SYS_REFCURSOR parameter (weakly-typed).</span></span>  
  
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
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a><span data-ttu-id="abe01-153">使用 WCF 客户端使用 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="abe01-153">Using REF CURSOR Parameters with a WCF Client</span></span>  
 <span data-ttu-id="abe01-154">若要通过使用 WCF 客户端调用过程或函数的 REF CURSOR 参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="abe01-154">To invoke a procedure or function with REF CURSOR parameters by using a WCF client, you do the following:</span></span>  
  
1. <span data-ttu-id="abe01-155">将字符串传递中的 for each 或 IN 出 REF CURSOR 参数，其中包含 PL/SQL 阻止打开 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="abe01-155">Pass a string for each IN or IN OUT REF CURSOR parameter that contains the PL/SQL block to open the REF CURSOR.</span></span> <span data-ttu-id="abe01-156">此块可以执行一个打开的 SELECT 语句，或调用的函数或在 OUT 参数返回打开的 REF CURSOR 的过程。</span><span class="sxs-lookup"><span data-stu-id="abe01-156">This block can either execute an OPEN FOR SELECT statement or invoke a function or procedure that returns an opened REF CURSOR in an OUT parameter.</span></span>  
  
2. <span data-ttu-id="abe01-157">过程或函数返回时，对操作中的任何 OUT 或 IN 出 REF CURSOR 参数所返回的记录集的数据。</span><span class="sxs-lookup"><span data-stu-id="abe01-157">When the procedure or function returns, operate on the data in the record sets returned for any OUT or IN OUT REF CURSOR parameters.</span></span> <span data-ttu-id="abe01-158">通用记录为弱类型化 REF CURSOR 参数设置或强类型的记录集的强类型化 REF CURSOR 参数，将记录集。</span><span class="sxs-lookup"><span data-stu-id="abe01-158">The record set will be a generic record set for weakly-typed REF CURSOR parameters or a strongly-typed record set for strongly-typed REF CURSOR parameters.</span></span>  
  
   <span data-ttu-id="abe01-159">有关如何使用 WCF 服务模型调用过程和函数的详细信息，请参阅[调用的函数和使用 WCF 服务模型的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="abe01-159">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
   <span data-ttu-id="abe01-160">下面的示例调用 GET_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="abe01-160">The following example calls the GET_ACTIVITY procedure.</span></span> <span data-ttu-id="abe01-161">它演示了这两种指定 IN REF CURSOR 参数：</span><span class="sxs-lookup"><span data-stu-id="abe01-161">It demonstrates both ways of specifying an IN REF CURSOR parameter:</span></span>  
  
- <span data-ttu-id="abe01-162">对于在 REF CURSOR 参数，一个打开的 SELECT 语句指定要为帐户 100001 返回活动。</span><span class="sxs-lookup"><span data-stu-id="abe01-162">For the IN REF CURSOR parameter, an OPEN FOR SELECT statement is specified to return activity for ACCOUNT 100001.</span></span>  
  
- <span data-ttu-id="abe01-163">对于在 OUT REF CURSOR 参数，调用该 /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY 过程。</span><span class="sxs-lookup"><span data-stu-id="abe01-163">For the IN OUT REF CURSOR parameter, the /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY procedure is invoked.</span></span> <span data-ttu-id="abe01-164">此过程将打开包含所有 ACCOUNTACTIVITY 表中的活动并将其作为一个输出参数返回 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="abe01-164">This procedure opens a REF CURSOR that contains all of the activity in the ACCOUNTACTIVITY table and returns it as an OUT parameter.</span></span>  
  
  <span data-ttu-id="abe01-165">该示例还演示如何读取从记录集的强类型化和弱类型化 REF CURSOR 参数返回的数据。</span><span class="sxs-lookup"><span data-stu-id="abe01-165">The example also demonstrates how to read data from the record set returned for both strongly-typed and weakly-typed REF CURSOR parameters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="abe01-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="abe01-166">See Also</span></span>  
 [<span data-ttu-id="abe01-167">开发 Oracle 数据库应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="abe01-167">Develop Oracle Database Application Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)