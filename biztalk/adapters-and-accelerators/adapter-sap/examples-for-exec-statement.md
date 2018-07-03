---
title: EXEC 语句示例 mySAP 适配器在 BizTalk 中的 |Microsoft Docs
description: EXEC 示例和示例使用 mySAP 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad2691f4-34bb-423c-9b3e-4abe2d55ddac
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59bdabcba48d00bdf1d6c884ae1f2b469d858626
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992590"
---
# <a name="examples-for-exec-statement"></a><span data-ttu-id="486ec-103">EXEC 语句示例</span><span class="sxs-lookup"><span data-stu-id="486ec-103">Examples for EXEC Statement</span></span>
<span data-ttu-id="486ec-104">本主题演示各种 EXEC 语句的示例语法。</span><span class="sxs-lookup"><span data-stu-id="486ec-104">This topic shows example syntax for various EXEC statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="486ec-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="486ec-105">Sample statements</span></span> 
  
-   <span data-ttu-id="486ec-106">若要执行没有任何输入参数的 BAPI，请使用以下语法;数据通过返回**DataReader**对象：</span><span class="sxs-lookup"><span data-stu-id="486ec-106">To execute a BAPI that takes no input parameters, use the following syntax; data is returned through a **DataReader** object:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST  
    ```  
  
-   <span data-ttu-id="486ec-107">若要执行采用输入的参数的 RFC，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="486ec-107">To execute an RFC that takes input parameters, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @NAME1='Contoso'  
    ```  
  
-   <span data-ttu-id="486ec-108">若要执行 RFC 采用输入的参数指定为变量，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="486ec-108">To execute an RFC that takes input parameters specified as a variable, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @var=@var  
    ```  
  
     <span data-ttu-id="486ec-109">在此示例中，必须创建一个名为参数`@var`和显式设置值 （例如，为 1001)，因为 RFC_CUSTOMER_GET 的第一个参数与 kunnr 相对应 （客户编号）</span><span class="sxs-lookup"><span data-stu-id="486ec-109">In this example, you must create a parameter named `@var` and set the value explicitly (for example, to 1001), because the first parameter for RFC_CUSTOMER_GET corresponds to KUNNR (Customer Number)</span></span>  
  
-   <span data-ttu-id="486ec-110">若要执行的输入的参数名称中使用变量的 RFC，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="486ec-110">To execute an RFC that uses a variable for the input parameter name, use the following syntax:</span></span>  
  
    ```  
    EXEC RFC_CUSTOMER_GET @KUNNR=@var1, @NAME1='Contoso'  
    ```  
  
     <span data-ttu-id="486ec-111">必须创建一个名为参数`@var1`、 指定的值，并将该类绑定到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="486ec-111">You must create a parameter named `@var1`, specify the value, and then bind it to the corresponding command object.</span></span> <span data-ttu-id="486ec-112">新创建的参数对象的默认方向是`input`。</span><span class="sxs-lookup"><span data-stu-id="486ec-112">The default direction of the newly created parameter object is `input`.</span></span>  
  
-   <span data-ttu-id="486ec-113">若要执行 BAPI 和返回表作为参数，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="486ec-113">To execute a BAPI and return tables as a parameter, use the following syntax:</span></span>  
  
    ```  
    EXEC BAPI_COMPANYCODE_GETLIST @COMPANYCODE_LIST=@var1 OUTPUT  
    ```  
  
     <span data-ttu-id="486ec-114">必须创建一个名为参数`@var1`、 指定的值，并将其绑定到相应的命令对象。</span><span class="sxs-lookup"><span data-stu-id="486ec-114">You must create a parameter named `@var1`, specify the value, and bind it to the corresponding command object.</span></span> <span data-ttu-id="486ec-115">应为新创建的参数对象的方向`InputOutput`或`Output`。</span><span class="sxs-lookup"><span data-stu-id="486ec-115">The direction of the newly created parameter object should be `InputOutput` or `Output`.</span></span>  
  
-   <span data-ttu-id="486ec-116">以下 EXEC 示例使用表的复杂类型参数。</span><span class="sxs-lookup"><span data-stu-id="486ec-116">The following EXEC example uses a table complex type parameter.</span></span> <span data-ttu-id="486ec-117">在示例中，@fields是表参数。</span><span class="sxs-lookup"><span data-stu-id="486ec-117">In the example, @fields is a TABLE parameter.</span></span>  
  
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
  
-   <span data-ttu-id="486ec-118">以下 EXEC 示例使用结构复杂类型。</span><span class="sxs-lookup"><span data-stu-id="486ec-118">The following EXEC example uses a STRUCT complex type.</span></span> <span data-ttu-id="486ec-119">在示例中，@equimaster是结构参数。</span><span class="sxs-lookup"><span data-stu-id="486ec-119">In the example, @equimaster is a STRUCT parameter.</span></span>  
  
    ```  
    exec BAPI_EQMT_MODIFY @equipment='000000000000000637', @equimaster='<EQUIMASTER>           
                <EQUIPMENT xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">equip</EQUIPMENT>  
                <EQUICATGRY xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">E</EQUICATGRY>  
                <MATERIAL xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">mat</MATERIAL>  
              </EQUIMASTER >', @equimaster=@em output  
    ```  
  
## <a name="support-for-complex-parameter-types"></a><span data-ttu-id="486ec-120">对复杂参数类型的支持</span><span class="sxs-lookup"><span data-stu-id="486ec-120">Support for Complex Parameter Types</span></span>  
 <span data-ttu-id="486ec-121">有两种方法以支持复杂的 RFC 参数 （表和结构） 时使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="486ec-121">There are two ways to support complex RFC parameters (tables and structures) when you use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
- <span data-ttu-id="486ec-122">复杂类型提供内联的 XML 值。</span><span class="sxs-lookup"><span data-stu-id="486ec-122">Provide an inline XML value for the complex type.</span></span> <span data-ttu-id="486ec-123">此示例演示如何将 XML 传递到复杂的参数类型*字段*。</span><span class="sxs-lookup"><span data-stu-id="486ec-123">This example shows how to pass XML to the complex parameter type *fields*.</span></span> <span data-ttu-id="486ec-124">在以下示例中， <em>@fields</em>是表参数。</span><span class="sxs-lookup"><span data-stu-id="486ec-124">In the following example, <em>@fields</em> is a table parameter.</span></span>  
  
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
  
- <span data-ttu-id="486ec-125">创建**DataTable**参数中的复杂类型并设置 SAP 参数值的字段的列与**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="486ec-125">Create a **DataTable** parameter with columns for the fields in the complex type and set the SAP parameter value to **DataTable**.</span></span> <span data-ttu-id="486ec-126">此示例演示如何设置@fields通过使用复杂类型**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="486ec-126">This example shows how to set the @fields complex type by using a **DataTable**.</span></span>  
  
  ```  
  cmd.CommandText = "exec rfc_read_table @query_table='BNKA', @fields = @p_fields";  
  DataTable dt = new DataTable();  
  dt.Columns.Add("FIELDNAME");  
  SAPParameter p = new SAPParameter("@p_fields");  
  p.Value = dt;  
  ```  
  
## <a name="limitations"></a><span data-ttu-id="486ec-127">限制</span><span class="sxs-lookup"><span data-stu-id="486ec-127">Limitations</span></span>  
 <span data-ttu-id="486ec-128">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]具有以下限制的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="486ec-128">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] has the following limitations for complex types.</span></span>  
  
- <span data-ttu-id="486ec-129">当传递复杂类型的参数中使用**DataTable**，必须包括所有字段 （列） 中的复杂类型的**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="486ec-129">When you pass a complex type in a parameter by using a **DataTable**, you must include all fields (columns) of the complex type in the **DataTable**.</span></span>  
  
- <span data-ttu-id="486ec-130">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]不支持**DbNull**。</span><span class="sxs-lookup"><span data-stu-id="486ec-130">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] does not support **DbNull**.</span></span> <span data-ttu-id="486ec-131">不能设置**DbNull**作为参数的值。</span><span class="sxs-lookup"><span data-stu-id="486ec-131">You cannot set **DbNull** as a value for parameters.</span></span>  
  
