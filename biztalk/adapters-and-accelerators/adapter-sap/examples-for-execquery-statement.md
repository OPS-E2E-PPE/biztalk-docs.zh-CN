---
title: EXECQUERY 语句示例 mySAP 适配器在 BizTalk 中的 |Microsoft Docs
description: EXECQUERY 示例和示例使用 mySAP 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631780b540d37e80c9218fc03f58b628e6d6e7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373476"
---
# <a name="examples-for-execquery-statement"></a><span data-ttu-id="a7f18-103">EXECQUERY 语句示例</span><span class="sxs-lookup"><span data-stu-id="a7f18-103">Examples for EXECQUERY Statement</span></span>
<span data-ttu-id="a7f18-104">本主题提供了示例 EXECQUERY 语句。</span><span class="sxs-lookup"><span data-stu-id="a7f18-104">This topic provides sample EXECQUERY statements.</span></span>  


## <a name="sample-statements"></a><span data-ttu-id="a7f18-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="a7f18-105">Sample statements</span></span>
-   <span data-ttu-id="a7f18-106">若要执行的查询，采用 P1 和 P2 两个参数的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-106">Command to execute a query that takes two parameters P1 and P2.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   <span data-ttu-id="a7f18-107">若要执行的查询采用参数 P1 的值的范围中的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-107">Command to execute a query that takes a range of value for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="a7f18-108">若要执行的查询，采用特定的范围之外的参数 P1 的值的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-108">Command to execute a query that takes values for parameter P1 outside a particular range.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="a7f18-109">若要执行的查询，可以采用参数 P1 的两个值之一的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-109">Command to execute a query that can take one of two values for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   <span data-ttu-id="a7f18-110">若要执行的查询，不能采用参数的特定值的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-110">Command to execute a query that cannot take specific values for parameters.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     <span data-ttu-id="a7f18-111">在此示例中，P1 可以具有"0000003262"以外的任何值。</span><span class="sxs-lookup"><span data-stu-id="a7f18-111">In this example, P1 can have any value other than '0000003262'.</span></span> <span data-ttu-id="a7f18-112">同样，P2 可以具有"0000003263"以外的任何值。</span><span class="sxs-lookup"><span data-stu-id="a7f18-112">Similarly, P2 can have any value other than '0000003263'.</span></span>  
  
-   <span data-ttu-id="a7f18-113">要执行具有变体在 SAP 系统中定义的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-113">Command to execute a query that has variants defined in the SAP system.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     <span data-ttu-id="a7f18-114">变体是指已保存的一组选择条件可以执行 SAP 查询时指定的。</span><span class="sxs-lookup"><span data-stu-id="a7f18-114">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="a7f18-115">例如，变体可用于指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="a7f18-115">For example, you can use variants to specify default values for queries.</span></span> <span data-ttu-id="a7f18-116">对于具有定义的所有参数的变量的查询，不需要命令文本中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="a7f18-116">For queries that have variants defined for all parameters, you do not need to specify the parameters in the command text.</span></span>  
  
-   <span data-ttu-id="a7f18-117">若要执行的查询，不需要参数的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-117">Command to execute a query that does not require a parameter.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     <span data-ttu-id="a7f18-118">对于不采用参数的查询，必须指定参数，使用虚拟值。</span><span class="sxs-lookup"><span data-stu-id="a7f18-118">For queries that do not take parameter, you must specify a parameter with a dummy value.</span></span>  
  
-   <span data-ttu-id="a7f18-119">要执行包含的参数应为日期值的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-119">Command to execute a query containing a parameter expecting a date value.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     <span data-ttu-id="a7f18-120">对于采用参数应为日期值的查询，必须指定日期，为 YYYYMMDD。</span><span class="sxs-lookup"><span data-stu-id="a7f18-120">For queries that take parameters expecting date values, you must specify the date as YYYYMMDD.</span></span>  
  
-   <span data-ttu-id="a7f18-121">若要通过指定参数的 null 值执行查询的命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-121">Command to execute a query by specifying null values for parameters.</span></span>  
  
     <span data-ttu-id="a7f18-122">对于此类查询，不能指定为查询：</span><span class="sxs-lookup"><span data-stu-id="a7f18-122">For such queries, you cannot specify a query as:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     <span data-ttu-id="a7f18-123">相反，如果您不想要指定一个值，不应指定 P1 根本。</span><span class="sxs-lookup"><span data-stu-id="a7f18-123">Instead, if you do not want to specify a value, you should not specify P1 at all.</span></span>  
  
-   <span data-ttu-id="a7f18-124">要执行包含需要值大于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-124">Command to execute a query containing a parameter expecting a value greater than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   <span data-ttu-id="a7f18-125">要执行包含需要值的参数的查询命令小于一定数量。</span><span class="sxs-lookup"><span data-stu-id="a7f18-125">Command to execute a query containing a parameter expecting a value lesser than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   <span data-ttu-id="a7f18-126">要执行包含需要值大于或等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-126">Command to execute a query containing a parameter expecting a value greater or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   <span data-ttu-id="a7f18-127">要执行包含需要值较小或等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-127">Command to execute a query containing a parameter expecting a value lesser or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   <span data-ttu-id="a7f18-128">要执行包含需要值不等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="a7f18-128">Command to execute a query containing a parameter expecting a value not equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  