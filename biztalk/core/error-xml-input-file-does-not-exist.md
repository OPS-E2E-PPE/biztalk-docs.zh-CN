---
title: 错误-XML 输入文件不存在 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xmlInputFileDoesNotExist
ms.assetid: d222e615-60c8-46f5-a8de-fc59650978c7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 202d86ceee251db8a2ae66f85ac90f005e311f53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346198"
---
# <a name="error---xml-input-file-does-not-exist"></a><span data-ttu-id="43683-102">错误-XML 输入文件不存在</span><span class="sxs-lookup"><span data-stu-id="43683-102">Error - XML Input File Does Not Exist</span></span>
<span data-ttu-id="43683-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="43683-103">**Error Code**</span></span>  
  
 <span data-ttu-id="43683-104">btm1039</span><span class="sxs-lookup"><span data-stu-id="43683-104">btm1039</span></span>  
  
 <span data-ttu-id="43683-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="43683-105">**Explanation**</span></span>  
  
 <span data-ttu-id="43683-106">为测试映射操作指定的 XML 输入的实例消息文件不存在。</span><span class="sxs-lookup"><span data-stu-id="43683-106">The XML input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="43683-107">时的值**测试映射输入**映射属性设置为 XML，则必须指定现有的 XML 实例消息文件的**测试映射输入实例**将属性映射。</span><span class="sxs-lookup"><span data-stu-id="43683-107">When the value of the **TestMap Input** map property is set to XML, you must specify an existing XML instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="43683-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="43683-108">**User Action**</span></span>  
  
 <span data-ttu-id="43683-109">右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**对话框的映射，请单击省略号 （**...**) 中的值字段按钮**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="43683-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="43683-110">使用**选择输入文件**对话框中，选择现有的 XML 实例与该映射的源架构一致的消息文件。</span><span class="sxs-lookup"><span data-stu-id="43683-110">Using the **Select Input File** dialog box, select an existing XML instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="43683-111">或者，直接的值字段中键入此 XML 文件的路径**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="43683-111">Alternatively, you can type the path of this XML file directly into the value field of the **TestMap Input Instance** property.</span></span>