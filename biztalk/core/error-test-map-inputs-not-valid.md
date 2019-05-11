---
title: 错误-测试映射输入无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81aca2f6d941f281a2a720250714c76798762e6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346574"
---
# <a name="error---test-map-inputs-not-valid"></a><span data-ttu-id="bf234-102">错误-测试映射输入无效</span><span class="sxs-lookup"><span data-stu-id="bf234-102">Error - Test Map Inputs Not Valid</span></span>
<span data-ttu-id="bf234-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="bf234-103">**Error Code**</span></span>  
  
 <span data-ttu-id="bf234-104">btm1036</span><span class="sxs-lookup"><span data-stu-id="bf234-104">btm1036</span></span>  
  
 <span data-ttu-id="bf234-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf234-105">**Explanation**</span></span>  
  
 <span data-ttu-id="bf234-106">已为测试映射操作指定任何输入的实例消息文件和测试映射输入的类型未设置为**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="bf234-106">No input instance message file has been specified for the Test Map operation, and the type of the TestMap input is not set to **Generate Instance**.</span></span> <span data-ttu-id="bf234-107">时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定实例消息文件**测试映射输入实例**映射属性。</span><span class="sxs-lookup"><span data-stu-id="bf234-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="bf234-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="bf234-108">**User Action**</span></span>  
  
 <span data-ttu-id="bf234-109">根据需要，设置一个或多个以下映射属性：</span><span class="sxs-lookup"><span data-stu-id="bf234-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="bf234-110">**测试映射输入实例。**</span><span class="sxs-lookup"><span data-stu-id="bf234-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="bf234-111">右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**对话框的映射，请单击省略号 （**...**) 中的值字段按钮**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="bf234-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="bf234-112">使用**选择输入文件**对话框中，选择的实例消息与映射的源架构一致的文件。</span><span class="sxs-lookup"><span data-stu-id="bf234-112">Using the **Select Input File** dialog box, select an instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="bf234-113">或者，直接的值字段中键入此文件的路径**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="bf234-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="bf234-114">**测试映射输入。**</span><span class="sxs-lookup"><span data-stu-id="bf234-114">**TestMap Input.**</span></span> <span data-ttu-id="bf234-115">若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**的映射中，使用下拉列表中的值字段对话框**测试映射输入**属性选择**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="bf234-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="bf234-116">在这种情况下，您需要指定的文件**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="bf234-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>