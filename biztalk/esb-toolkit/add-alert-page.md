---
title: 添加警报页 |Microsoft Docs
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
ms.openlocfilehash: c60c0b495a4d472ea45f9622e61b6a6deb9d95dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400146"
---
# <a name="add-alert-page"></a><span data-ttu-id="ae0e5-102">添加警报页</span><span class="sxs-lookup"><span data-stu-id="ae0e5-102">Add Alert Page</span></span>
<span data-ttu-id="ae0e5-103">图 1 显示了可以在其中创建新的警报相匹配的警报中指定的条件 （条件） 的错误消息到达门户时，将引发在门户的添加警报页。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-103">Figure 1 shows the Add Alert page, where you can create a new alert that the portal will raise when a fault message matching the criteria (conditions) specified in the alert arrives at the portal.</span></span>  
  
 <span data-ttu-id="ae0e5-104">![添加警报页](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")</span><span class="sxs-lookup"><span data-stu-id="ae0e5-104">![Add Alert Page](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")</span></span>  
  
 <span data-ttu-id="ae0e5-105">**图 1**</span><span class="sxs-lookup"><span data-stu-id="ae0e5-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="ae0e5-106">**ESB 管理门户添加警报页**</span><span class="sxs-lookup"><span data-stu-id="ae0e5-106">**The ESB Management Portal Add Alert page**</span></span>  
  
 <span data-ttu-id="ae0e5-107">在添加警报页，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-107">On the Add Alert page, you can do the following:</span></span>  
  
-   <span data-ttu-id="ae0e5-108">键入新警报的名称**输入警报名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-108">Type a name for the new alert in the **Enter Alert Name** text box.</span></span>  
  
-   <span data-ttu-id="ae0e5-109">指定如何将警报匹配到中的传入异常中字段的值**添加为此警报的条件**此页面部分。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-109">Specify how the alert will match to values of the fields in incoming exceptions in the **Add conditions for this alert** section of this page.</span></span> <span data-ttu-id="ae0e5-110">从异常架构选择一个字段 (如**应用程序、 错误类型**或**故障严重性)** 中**条件**下拉列表; 选择比较类型的 （例如，如 =、 **！ =、 > =、 < =、** 或**等**) 中**运算符**下拉列表; 并键入或选择第三个列表中的值。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-110">Select a field from the exception schema (such as **Application, Error Type,** or **Fault Severity)** in the **Criteria** drop-down list; select a comparison type for the (such as =, **!=, >=, <=,** or **like**) in the **Operator** drop-down list; and type or select a value from the third list.</span></span> <span data-ttu-id="ae0e5-111">当您选择的异常字段中，**值**控件更改为文本框或下拉列表，以便输入或选择匹配的值。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-111">When you select an exception field, the **Value** control changes to either a text box or a drop-down list for you to enter or select a matching value.</span></span>  
  
-   <span data-ttu-id="ae0e5-112">在选择或输入条件值，单击**添加**链接以添加到列表中的这种情况**条件**部分页上，并重复添加任何需要为此警报的更多条件.</span><span class="sxs-lookup"><span data-stu-id="ae0e5-112">After selecting or entering the criteria values, click the **Add** link to add this condition to the list in the **Conditions** section of the page, and repeat to add any more conditions you require for this alert.</span></span>  
  
-   <span data-ttu-id="ae0e5-113">单击**保存**按钮以您指定的条件的名称与创建新的警报。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-113">Click the **Save** button to create the new alert with the name and conditions you specified.</span></span>