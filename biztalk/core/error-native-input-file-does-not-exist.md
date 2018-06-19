---
title: 错误-本机的输入的文件不存在 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241885"
---
# <a name="error---native-input-file-does-not-exist"></a><span data-ttu-id="3ec48-102">错误-本机的输入的文件不存在</span><span class="sxs-lookup"><span data-stu-id="3ec48-102">Error - Native Input File Does Not Exist</span></span>
<span data-ttu-id="3ec48-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="3ec48-103">**Error Code**</span></span>  
  
 <span data-ttu-id="3ec48-104">btm1040</span><span class="sxs-lookup"><span data-stu-id="3ec48-104">btm1040</span></span>  
  
 <span data-ttu-id="3ec48-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="3ec48-105">**Explanation**</span></span>  
  
 <span data-ttu-id="3ec48-106">为测试映射操作指定的本地输入实例消息文件不存在。</span><span class="sxs-lookup"><span data-stu-id="3ec48-106">The native input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="3ec48-107">时的值**测试映射输入**映射属性设置为**本机**，必须指定现有的本地实例消息文件进行**测试映射输入实例**映射属性。</span><span class="sxs-lookup"><span data-stu-id="3ec48-107">When the value of the **TestMap Input** map property is set to **Native**, you must specify an existing native instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="3ec48-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="3ec48-108">**User Action**</span></span>  
  
 <span data-ttu-id="3ec48-109">右键单击解决方案资源管理器中的相关映射，请单击**属性**，然后在**测试映射**选项卡中**属性页**对话框中的地图中，单击省略号 （**...**) 的值字段中的按钮**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="3ec48-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="3ec48-110">在**选择输入文件**对话框中，选择现有的本机实例符合映射的源架构的消息文件。</span><span class="sxs-lookup"><span data-stu-id="3ec48-110">In the **Select Input File** dialog box, select an existing native instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="3ec48-111">或者，直接的值字段中键入此本机文件的路径**测试映射输入实例**属性。</span><span class="sxs-lookup"><span data-stu-id="3ec48-111">Alternatively, you can type the path of this native file directly into the value field of the **TestMap Input Instance** property.</span></span>