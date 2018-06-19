---
title: EXECQUERY 语句中 BizTalk mySAP 适配器中的示例 |Microsoft 文档
description: EXECQUERY 示例和样本使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器
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
ms.openlocfilehash: 77c5d5877ff502b8fdca620d8b92e4427d3b73b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216237"
---
# <a name="examples-for-execquery-statement"></a><span data-ttu-id="3a28e-103">EXECQUERY 语句的示例</span><span class="sxs-lookup"><span data-stu-id="3a28e-103">Examples for EXECQUERY Statement</span></span>
<span data-ttu-id="3a28e-104">本主题提供示例 EXECQUERY 语句。</span><span class="sxs-lookup"><span data-stu-id="3a28e-104">This topic provides sample EXECQUERY statements.</span></span>  


## <a name="sample-statements"></a><span data-ttu-id="3a28e-105">示例语句</span><span class="sxs-lookup"><span data-stu-id="3a28e-105">Sample statements</span></span>
-   <span data-ttu-id="3a28e-106">若要执行的查询采用 P1 和 P2 两个参数的命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-106">Command to execute a query that takes two parameters P1 and P2.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   <span data-ttu-id="3a28e-107">若要执行的查询采用参数 P1 的值的范围中的命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-107">Command to execute a query that takes a range of value for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="3a28e-108">若要执行的查询采用参数 P1 超出特定范围的值的命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-108">Command to execute a query that takes values for parameter P1 outside a particular range.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="3a28e-109">要执行的查询，可以执行参数 P1 的两个值之一的命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-109">Command to execute a query that can take one of two values for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   <span data-ttu-id="3a28e-110">要执行不能采用参数的特定值的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-110">Command to execute a query that cannot take specific values for parameters.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     <span data-ttu-id="3a28e-111">在此示例中，P1 可以具有"0000003262"以外的任何值。</span><span class="sxs-lookup"><span data-stu-id="3a28e-111">In this example, P1 can have any value other than '0000003262'.</span></span> <span data-ttu-id="3a28e-112">同样，P2 可以具有"0000003263"以外的任何值。</span><span class="sxs-lookup"><span data-stu-id="3a28e-112">Similarly, P2 can have any value other than '0000003263'.</span></span>  
  
-   <span data-ttu-id="3a28e-113">要执行具有变体在 SAP 系统中定义的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-113">Command to execute a query that has variants defined in the SAP system.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     <span data-ttu-id="3a28e-114">变体，请参阅为已保存的一组可以执行的 SAP 查询时指定的选择条件。</span><span class="sxs-lookup"><span data-stu-id="3a28e-114">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="3a28e-115">例如，可以使用变体指定查询的默认值。</span><span class="sxs-lookup"><span data-stu-id="3a28e-115">For example, you can use variants to specify default values for queries.</span></span> <span data-ttu-id="3a28e-116">对于具有针对所有参数定义的变量的查询，你不需要在命令文本中指定的参数。</span><span class="sxs-lookup"><span data-stu-id="3a28e-116">For queries that have variants defined for all parameters, you do not need to specify the parameters in the command text.</span></span>  
  
-   <span data-ttu-id="3a28e-117">要执行不需要参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-117">Command to execute a query that does not require a parameter.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     <span data-ttu-id="3a28e-118">对于不带参数的查询，你必须指定一个虚拟值参数。</span><span class="sxs-lookup"><span data-stu-id="3a28e-118">For queries that do not take parameter, you must specify a parameter with a dummy value.</span></span>  
  
-   <span data-ttu-id="3a28e-119">要执行包含需要日期值的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-119">Command to execute a query containing a parameter expecting a date value.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     <span data-ttu-id="3a28e-120">对于采用参数应为日期值的查询，你必须指定日期作为 YYYYMMDD。</span><span class="sxs-lookup"><span data-stu-id="3a28e-120">For queries that take parameters expecting date values, you must specify the date as YYYYMMDD.</span></span>  
  
-   <span data-ttu-id="3a28e-121">要通过指定参数的 null 值执行查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-121">Command to execute a query by specifying null values for parameters.</span></span>  
  
     <span data-ttu-id="3a28e-122">对于此类查询，不能指定形式的查询：</span><span class="sxs-lookup"><span data-stu-id="3a28e-122">For such queries, you cannot specify a query as:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     <span data-ttu-id="3a28e-123">相反，如果你不希望指定一个值，你不应指定 P1 根本。</span><span class="sxs-lookup"><span data-stu-id="3a28e-123">Instead, if you do not want to specify a value, you should not specify P1 at all.</span></span>  
  
-   <span data-ttu-id="3a28e-124">要执行包含需要值大于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-124">Command to execute a query containing a parameter expecting a value greater than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   <span data-ttu-id="3a28e-125">要执行包含需要值的参数的查询命令早于一定数量。</span><span class="sxs-lookup"><span data-stu-id="3a28e-125">Command to execute a query containing a parameter expecting a value lesser than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   <span data-ttu-id="3a28e-126">要执行包含需要值大于或等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-126">Command to execute a query containing a parameter expecting a value greater or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   <span data-ttu-id="3a28e-127">要执行包含预期值的较小或等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-127">Command to execute a query containing a parameter expecting a value lesser or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   <span data-ttu-id="3a28e-128">要执行包含预期值不等于一定数量的参数的查询命令。</span><span class="sxs-lookup"><span data-stu-id="3a28e-128">Command to execute a query containing a parameter expecting a value not equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  