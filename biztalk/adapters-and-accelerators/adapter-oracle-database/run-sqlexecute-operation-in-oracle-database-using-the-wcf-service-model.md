---
title: 在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, performing a SQLEXECUTE operation
- SQLEXECUTE operation, performing a
- how to, invoke the SQLEXECUTE operation
ms.assetid: d3f61e5f-4453-4a76-9bc6-40d91cb58224
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf001bcfe96a2fb6849ce72ba5800117f62e618c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376063"
---
# <a name="run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="c3256-102">在 Oracle 数据库中使用 WCF 服务模型运行 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="c3256-102">Run SQLEXECUTE operation in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="c3256-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组标准的 Oracle 数据库项目上的操作。</span><span class="sxs-lookup"><span data-stu-id="c3256-103">The[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="c3256-104">通过使用这些操作，可以执行诸如调用 Oracle 函数或过程，或执行对表的基本 SQL 数据操作语言 (DML) 操作。</span><span class="sxs-lookup"><span data-stu-id="c3256-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="c3256-105">但是，可能有需要你执行操作的方案由您的业务逻辑驱动的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。</span><span class="sxs-lookup"><span data-stu-id="c3256-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="c3256-106">例如，您可能希望：</span><span class="sxs-lookup"><span data-stu-id="c3256-106">For example, you may want to:</span></span>  
  
- <span data-ttu-id="c3256-107">不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。</span><span class="sxs-lookup"><span data-stu-id="c3256-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
- <span data-ttu-id="c3256-108">执行数据定义语言操作;例如，创建一个表。</span><span class="sxs-lookup"><span data-stu-id="c3256-108">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
- <span data-ttu-id="c3256-109">如果没有安装在设计时用于数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。</span><span class="sxs-lookup"><span data-stu-id="c3256-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
- <span data-ttu-id="c3256-110">执行更复杂的表比操作的 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示; 例如，若要执行查询，包括对 JOIN 子句。</span><span class="sxs-lookup"><span data-stu-id="c3256-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
  <span data-ttu-id="c3256-111">对于这些类型的情况下， [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作的图面。</span><span class="sxs-lookup"><span data-stu-id="c3256-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="c3256-112">通过使用 SQLEXECUTE 操作，可以对 Oracle 数据库执行参数化的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="c3256-112">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="c3256-113">SQLEXECUTE 操作支持的输入的参数块组成，您可以执行一次为每个集的同一 SQL 语句的参数集。</span><span class="sxs-lookup"><span data-stu-id="c3256-113">The SQLEXECUTE operation supports an input parameter block comprised of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="c3256-114">SQLEXECUTE 操作返回中泛型的记录集的 SQL 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="c3256-114">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="c3256-115">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="c3256-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="c3256-116">本主题使用 Oracle 序列中的示例名为 TID_SEQ。</span><span class="sxs-lookup"><span data-stu-id="c3256-116">The examples in this topic use an Oracle SEQUENCE named TID_SEQ.</span></span> <span data-ttu-id="c3256-117">使用 SDK 示例提供了一个脚本来生成此序列。</span><span class="sxs-lookup"><span data-stu-id="c3256-117">A script to generate this SEQUENCE is supplied with the SDK samples.</span></span> <span data-ttu-id="c3256-118">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="c3256-118">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="c3256-119">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="c3256-119">The WCF Client Class</span></span>  
 <span data-ttu-id="c3256-120">WCF 服务模型生成专用的 WCF 客户端**SQLEXECUTEClient**，SQLEXECUTE 操作的。</span><span class="sxs-lookup"><span data-stu-id="c3256-120">The WCF service model generates a dedicated WCF client, **SQLEXECUTEClient**, for the SQLEXECUTE operation.</span></span> <span data-ttu-id="c3256-121">下面的代码演示**SQLEXECUTEClient**和调用来调用 SQLEXECUTE 操作的方法的签名。</span><span class="sxs-lookup"><span data-stu-id="c3256-121">The following code shows the **SQLEXECUTEClient** and the signature of the method that you call to invoke the SQLEXECUTE operation.</span></span>  
  
```  
public partial class SQLEXECUTEClient : System.ServiceModel.ClientBase<SQLEXECUTE>, SQLEXECUTE {  
  
    ...  
  
    public microsoft.lobservices.oracledb._2007._03.GenRecordRow[] SQLEXECUTE(string SQLSTATEMENT, string PARAMETERSCHEMA, microsoft.lobservices.oracledb._2007._03.PARAMETERDATA[] PARAMETERSET);   
}  
```  
  
 <span data-ttu-id="c3256-122">SQLEXECUTE 操作将返回通用的记录集。</span><span class="sxs-lookup"><span data-stu-id="c3256-122">The SQLEXECUTE operation returns a generic record set.</span></span> <span data-ttu-id="c3256-123">此记录集包含的值 （如果有） 返回的语句执行该 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="c3256-123">This record set contains the values (if any) that are returned by the statements that the SQLEXECUTE operation executes.</span></span> <span data-ttu-id="c3256-124">可以向其中每个包含一系列表示为字符串的输入参数 PARAMETERDATA 对象的集合中的 SQLEXECUTE 操作传递输入参数的集。</span><span class="sxs-lookup"><span data-stu-id="c3256-124">You can pass sets of input parameters to the SQLEXECUTE operation in a collection of PARAMETERDATA objects, each of which contains a collection of input parameters represented as strings.</span></span> <span data-ttu-id="c3256-125">下面的代码演示 PARAMETERDATA 集的定义。</span><span class="sxs-lookup"><span data-stu-id="c3256-125">The following code shows the definition of a PARAMETERDATA set.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class PARAMETERDATA : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private string[] PARAMETERField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public string[] PARAMETER {  
            get {  
                return this.PARAMETERField;  
            }  
            set {  
                this.PARAMETERField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="invoking-the-sqlexecute-operation"></a><span data-ttu-id="c3256-126">调用 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="c3256-126">Invoking the SQLEXECUTE Operation</span></span>  
 <span data-ttu-id="c3256-127">若要通过使用 WCF 客户端调用 SQLEXECUTE 操作，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c3256-127">To invoke the SQLEXECUTE operation by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="c3256-128">生成**SQLEXECUTEClient**类为目标表或视图。</span><span class="sxs-lookup"><span data-stu-id="c3256-128">Generate a **SQLEXECUTEClient** class for the target table or view.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="c3256-129">SQLEXECUTE 操作显示在根节点下 (**/**) 中**选择一个类别**窗格中的**添加适配器服务引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="c3256-129">The SQLEXECUTE operation is surfaced under the root node (**/**) in the **Select a category** pane in the **Add Adapter Service Reference** dialog box.</span></span>  
  
2. <span data-ttu-id="c3256-130">创建的实例**SQLEXECUTEClient**类，并调用**SQLEXECUTE**要对 Oracle 数据库执行 SQL 语句的方法。</span><span class="sxs-lookup"><span data-stu-id="c3256-130">Create an instance of the **SQLEXECUTEClient** class, and invoke the **SQLEXECUTE** method to execute SQL statements on the Oracle database.</span></span>  
  
   <span data-ttu-id="c3256-131">有关更多详细信息，有关如何创建 WCF 客户端类，并在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="c3256-131">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF service model with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="c3256-132">下面的示例使用**SQLEXECUTEClient**若要获取 Oracle 序列，TID_SEQ，下一个值，通过执行以下 SQL 语句： `SELECT tid_seq.nextval id from DUAL`。</span><span class="sxs-lookup"><span data-stu-id="c3256-132">The following example uses the **SQLEXECUTEClient** to get the next value of an Oracle SEQUENCE, TID_SEQ, by executing the following SQL statement: `SELECT tid_seq.nextval id from DUAL`.</span></span> <span data-ttu-id="c3256-133">然后向控制台写入输出。</span><span class="sxs-lookup"><span data-stu-id="c3256-133">The output is then written to the console.</span></span>  
  
```  
using (SQLEXECUTEClient sqlClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE"))  
{  
    sqlClient.ClientCredentials.UserName.UserName = "SCOTT";  
    sqlClient.ClientCredentials.UserName.Password = "TIGER";  
    try  
    {  
        sqlClient.Open();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error opening SQL client " + ex.Message);  
        throw;  
    }  
    microsoft.lobservices.oracledb._2007._03.GenRecordRow[] sequenceRec =   
        new microsoft.lobservices.oracledb._2007._03.GenRecordRow[0];  
  
    try  
    {  
        sequenceRec = sqlClient.SQLEXECUTE("SELECT tid_seq.nextval id from DUAL", null, null);  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Error executing SQL client " + ex.Message);  
        throw;  
    }  
  
    if (sequenceRec.Length > 0)  
    {  
        Console.WriteLine("TID_SEQUENCE value is {0}", sequenceRec[0].GenRecordColumn[0].ColumnValue);  
    }  
    else  
    {  
    Console.WriteLine("Couldn't get next TID_SEQUENCE value");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3256-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3256-134">See Also</span></span>  
 [<span data-ttu-id="c3256-135">开发 Oracle 数据库应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="c3256-135">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)