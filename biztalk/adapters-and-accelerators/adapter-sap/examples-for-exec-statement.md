---
title: "EXEC 语句中 BizTalk mySAP 适配器中的示例 |Microsoft 文档"
description: "EXEC 示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eaae930d7d94d24bac9d484957ccf02718af60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="examples-for-exec-statement"></a><span data-ttu-id="2458d-103">EXEC 语句的示例</span><span class="sxs-lookup"><span data-stu-id="2458d-103">Examples for EXEC Statement</span></span>
<span data-ttu-id="2458d-104">本主题演示各种 EXEC 语句的示例语法。</span><span class="sxs-lookup"><span data-stu-id="2458d-104">This topic shows example syntax for various EXEC statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="2458d-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="2458d-105">Sample statements</span></span> 
  
-   <span data-ttu-id="2458d-106">若要执行不使用输入参数 BAPI，使用以下语法;通过返回数据**DataReader**对象：</span><span class="sxs-lookup"><span data-stu-id="2458d-106">To execute a BAPI that takes no input parameters, use the following syntax; data is returned through a **DataReader** object:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   <span data-ttu-id="2458d-107">若要执行的 RFC 都采用输入的参数，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2458d-107">To execute an RFC that takes input parameters, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   <span data-ttu-id="2458d-108">若要执行的 RFC 都采用为变量指定的输入的参数，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2458d-108">To execute an RFC that takes input parameters specified as a variable, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     <span data-ttu-id="2458d-109">在此示例中，你必须创建一个名为参数`@var`和显式设置值 （例如，到 1001)，因为 RFC_CUSTOMER_GET 的第一个参数对应于 KUNNR （客户编号）</span><span class="sxs-lookup"><span data-stu-id="2458d-109">In this example, you must create a parameter named `@var` and set the value explicitly (for example, to 1001), because the first parameter for RFC_CUSTOMER_GET corresponds to KUNNR (Customer Number)</span></span>  
  
-   <span data-ttu-id="2458d-110">若要执行的输入的参数名称中使用变量 RFC，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2458d-110">To execute an RFC that uses a variable for the input parameter name, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     <span data-ttu-id="2458d-111">你必须创建一个名为参数`@var1`，指定值，然后将其绑定到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="2458d-111">You must create a parameter named `@var1`, specify the value, and then bind it to the corresponding command object.</span></span> <span data-ttu-id="2458d-112">新创建的参数对象的默认方向是`input`。</span><span class="sxs-lookup"><span data-stu-id="2458d-112">The default direction of the newly created parameter object is `input`.</span></span>  
  
-   <span data-ttu-id="2458d-113">若要作为参数执行 BAPI 和返回的表，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2458d-113">To execute a BAPI and return tables as a parameter, use the following syntax:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     <span data-ttu-id="2458d-114">你必须创建一个名为参数`@var1`、 指定的值，并将其绑定到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="2458d-114">You must create a parameter named `@var1`, specify the value, and bind it to the corresponding command object.</span></span> <span data-ttu-id="2458d-115">应为新创建的参数对象的方向`InputOutput`或`Output`。</span><span class="sxs-lookup"><span data-stu-id="2458d-115">The direction of the newly created parameter object should be `InputOutput` or `Output`.</span></span>  
  
-   <span data-ttu-id="2458d-116">下面的 EXEC 示例使用表复杂类型参数。</span><span class="sxs-lookup"><span data-stu-id="2458d-116">The following EXEC example uses a table complex type parameter.</span></span> <span data-ttu-id="2458d-117">在示例中，@fields是表参数。</span><span class="sxs-lookup"><span data-stu-id="2458d-117">In the example, @fields is a TABLE parameter.</span></span>  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   <span data-ttu-id="2458d-118">下面的 EXEC 示例使用结构复杂类型。</span><span class="sxs-lookup"><span data-stu-id="2458d-118">The following EXEC example uses a STRUCT complex type.</span></span> <span data-ttu-id="2458d-119">在示例中，@equimaster是结构参数。</span><span class="sxs-lookup"><span data-stu-id="2458d-119">In the example, @equimaster is a STRUCT parameter.</span></span>  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a><span data-ttu-id="2458d-120">对复杂的参数类型的支持</span><span class="sxs-lookup"><span data-stu-id="2458d-120">Support for Complex Parameter Types</span></span>  
 <span data-ttu-id="2458d-121">有两种方法，以支持复杂的 RFC 参数 （表和结构） 时使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2458d-121">There are two ways to support complex RFC parameters (tables and structures) when you use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
-   <span data-ttu-id="2458d-122">复杂类型的提供内联的 XML 值。</span><span class="sxs-lookup"><span data-stu-id="2458d-122">Provide an inline XML value for the complex type.</span></span> <span data-ttu-id="2458d-123">此示例演示如何将 XML 传递给复杂的参数类型*字段*。</span><span class="sxs-lookup"><span data-stu-id="2458d-123">This example shows how to pass XML to the complex parameter type *fields*.</span></span> <span data-ttu-id="2458d-124">在下面的示例中，  *@fields* 是表参数。</span><span class="sxs-lookup"><span data-stu-id="2458d-124">In the following example, *@fields* is a table parameter.</span></span>  
  
    ```  
    exec rfc_read_table @query_table='BNKA', @fields='<FIELDS xmlns='http://Microsoft.LobServices.Sap/2007/03/Rfc/'>  
                <RFC_DB_FLD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                  <FIELDNAME>BANKL</FIELDNAME>  
                </RFC_DB_FLD>  
                <RFC_DB_FLD  xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
                    <FIELDNAME>BANKS</FIELDNAME>  
                </RFC_DB_FLD>  
              </FIELDS>', @fields=@flds output  
    ```  
  
-   <span data-ttu-id="2458d-125">创建**DataTable**参数中的复杂类型和 SAP 参数值的集的字段的列**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="2458d-125">Create a **DataTable** parameter with columns for the fields in the complex type and set the SAP parameter value to **DataTable**.</span></span> <span data-ttu-id="2458d-126">此示例演示如何设置@fields使用复杂类型**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="2458d-126">This example shows how to set the @fields complex type by using a **DataTable**.</span></span>  
  
    ```  
    cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
    DataTable dt = new DataTable();  
    dt.Columns.Add("FIELDNAME");  
    SAPParameter p = new SAPParameter("@p_fields");  
    p.Value = dt;  
    ```  
  
## <a name="limitations"></a><span data-ttu-id="2458d-127">限制</span><span class="sxs-lookup"><span data-stu-id="2458d-127">Limitations</span></span>  
 <span data-ttu-id="2458d-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]具有以下限制为复杂类型。</span><span class="sxs-lookup"><span data-stu-id="2458d-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] has the following limitations for complex types.</span></span>  
  
-   <span data-ttu-id="2458d-129">传递时，复杂类型参数中使用**DataTable**，必须包括所有字段 （列） 中的复杂类型**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="2458d-129">When you pass a complex type in a parameter by using a **DataTable**, you must include all fields (columns) of the complex type in the **DataTable**.</span></span>  
  
-   <span data-ttu-id="2458d-130">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]不支持**DbNull**。</span><span class="sxs-lookup"><span data-stu-id="2458d-130">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] does not support **DbNull**.</span></span> <span data-ttu-id="2458d-131">无法设置**DbNull**作为参数的值。</span><span class="sxs-lookup"><span data-stu-id="2458d-131">You cannot set **DbNull** as a value for parameters.</span></span>  
  
