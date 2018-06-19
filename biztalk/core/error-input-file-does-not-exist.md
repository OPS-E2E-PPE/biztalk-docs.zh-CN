---
title: 错误-输入的文件不存在 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241797"
---
# <a name="error---input-file-does-not-exist"></a><span data-ttu-id="17f24-102">错误-输入的文件不存在</span><span class="sxs-lookup"><span data-stu-id="17f24-102">Error - Input File Does Not Exist</span></span>
<span data-ttu-id="17f24-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="17f24-103">**Error Code**</span></span>  
  
 <span data-ttu-id="17f24-104">btm1037</span><span class="sxs-lookup"><span data-stu-id="17f24-104">btm1037</span></span>  
  
 <span data-ttu-id="17f24-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="17f24-105">**Explanation**</span></span>  
  
 <span data-ttu-id="17f24-106">为测试映射操作不存在，并输入测试映射的类型未设置为指定的输入的实例消息文件**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="17f24-106">The input instance message file specified for the Test Map operation does not exist, and the type of the Test Map input is not set to **Generate Instance**.</span></span> <span data-ttu-id="17f24-107">时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定现有的实例消息文件进行**测试映射输入实例**将属性映射。</span><span class="sxs-lookup"><span data-stu-id="17f24-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an existing instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="17f24-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="17f24-108">**User Action**</span></span>  
  
 <span data-ttu-id="17f24-109">根据需要，设置下面任一映射属性：</span><span class="sxs-lookup"><span data-stu-id="17f24-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="17f24-110">**测试映射输入实例。**</span><span class="sxs-lookup"><span data-stu-id="17f24-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="17f24-111">右键单击解决方案资源管理器中的相关映射，请单击**属性**，然后在**测试映射**选项卡中**属性页**对话框中的地图中，单击省略号 （**...**) 的值字段中的按钮**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="17f24-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="17f24-112">使用**选择输入文件**对话框中，选择现有实例消息符合映射的源架构的文件。</span><span class="sxs-lookup"><span data-stu-id="17f24-112">Using the **Select Input File** dialog box, select an existing instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="17f24-113">或者，你可以直接的值字段中键入此文件的路径**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="17f24-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="17f24-114">**测试映射输入。**</span><span class="sxs-lookup"><span data-stu-id="17f24-114">**TestMap Input.**</span></span> <span data-ttu-id="17f24-115">若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射中，单击**属性**，然后在**测试映射**选项卡**属性页**对于映射，使用下拉列表中的值字段中的对话框**测试映射输入**属性以选择**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="17f24-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab of the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="17f24-116">在这种情况下，不需要指定的文件**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="17f24-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>