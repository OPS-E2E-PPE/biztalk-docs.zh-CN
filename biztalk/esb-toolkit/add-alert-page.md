---
title: 添加警报页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa93a777481c905dbedfffe5e7675335c4aec40b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290421"
---
# <a name="add-alert-page"></a><span data-ttu-id="5408e-102">“添加警报”页</span><span class="sxs-lookup"><span data-stu-id="5408e-102">Add Alert Page</span></span>
<span data-ttu-id="5408e-103">图 1 显示你可以在其中创建新的警报，门户将引发当匹配警报中指定的条件 （条件） 的错误消息到达门户的添加警报页。</span><span class="sxs-lookup"><span data-stu-id="5408e-103">Figure 1 shows the Add Alert page, where you can create a new alert that the portal will raise when a fault message matching the criteria (conditions) specified in the alert arrives at the portal.</span></span>  
  
 <span data-ttu-id="5408e-104">![添加警报页](../esb-toolkit/media/ch8-addalertpage.gif "Ch8 AddAlertPage")</span><span class="sxs-lookup"><span data-stu-id="5408e-104">![Add Alert Page](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")</span></span>  
  
 <span data-ttu-id="5408e-105">**图 1**</span><span class="sxs-lookup"><span data-stu-id="5408e-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="5408e-106">**ESB 管理门户添加警报页**</span><span class="sxs-lookup"><span data-stu-id="5408e-106">**The ESB Management Portal Add Alert page**</span></span>  
  
 <span data-ttu-id="5408e-107">在添加警报页可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5408e-107">On the Add Alert page, you can do the following:</span></span>  
  
-   <span data-ttu-id="5408e-108">键入新警报中的名称**输入警报名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="5408e-108">Type a name for the new alert in the **Enter Alert Name** text box.</span></span>  
  
-   <span data-ttu-id="5408e-109">指定警报中的传入异常中的字段的值的匹配方式**添加此警报的条件**的此页的部分。</span><span class="sxs-lookup"><span data-stu-id="5408e-109">Specify how the alert will match to values of the fields in incoming exceptions in the **Add conditions for this alert** section of this page.</span></span> <span data-ttu-id="5408e-110">从异常架构选择一个字段 (如**应用程序，错误类型**或**故障严重性)** 中**条件**下拉列表; 选择比较类型 （例如如 =、 **！ =、 > =、 < =、** 或**如**) 中**运算符**下拉列表; 并键入或选择第三个列表中的值。</span><span class="sxs-lookup"><span data-stu-id="5408e-110">Select a field from the exception schema (such as **Application, Error Type,** or **Fault Severity)** in the **Criteria** drop-down list; select a comparison type for the (such as =, **!=, >=, <=,** or **like**) in the **Operator** drop-down list; and type or select a value from the third list.</span></span> <span data-ttu-id="5408e-111">当你选择的异常字段中，**值**控件更改到文本框中或供你输入或选择一个匹配值的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5408e-111">When you select an exception field, the **Value** control changes to either a text box or a drop-down list for you to enter or select a matching value.</span></span>  
  
-   <span data-ttu-id="5408e-112">选择或输入的条件值后, 单击**添加**链接到的列表中添加此条件**条件**页和重复添加任何更多条件，你需要为此警报的部分.</span><span class="sxs-lookup"><span data-stu-id="5408e-112">After selecting or entering the criteria values, click the **Add** link to add this condition to the list in the **Conditions** section of the page, and repeat to add any more conditions you require for this alert.</span></span>  
  
-   <span data-ttu-id="5408e-113">单击**保存**按钮以名称和你指定的条件创建新的警报。</span><span class="sxs-lookup"><span data-stu-id="5408e-113">Click the **Save** button to create the new alert with the name and conditions you specified.</span></span>