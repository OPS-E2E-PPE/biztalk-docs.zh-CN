---
title: 重新发送状态详细信息报表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2335b10da205258f32a6676a6fee2a3ff32fef65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268413"
---
# <a name="resend-status-details-report"></a><span data-ttu-id="4733c-102">重新发送状态详细信息报告</span><span class="sxs-lookup"><span data-stu-id="4733c-102">Resend Status Details Report</span></span>
<span data-ttu-id="4733c-103">将参与方的“作为 AS2 接收方的参与方”属性配置为在未收到 MDN 情况下重新发送 AS2 消息时，此状态报告显示有关所做的重试信息。</span><span class="sxs-lookup"><span data-stu-id="4733c-103">This status report displays information on retry attempts made when the Party as AS2 Receiver properties of a party are configured to resend the AS2 message if an MDN is not received.</span></span>  
  
 <span data-ttu-id="4733c-104">此报表显示通过一条消息在 AS2/MDN 状态报表中，右键单击，然后单击**查看可靠消息传递状态**。</span><span class="sxs-lookup"><span data-stu-id="4733c-104">You display this report by right-clicking on a message in the AS2/MDN status report, and then clicking **View Reliable Messaging Status**.</span></span> <span data-ttu-id="4733c-105">随后，“重新发送状态详细信息”页将显示对此消息所做的重新发送尝试的相关信息。</span><span class="sxs-lookup"><span data-stu-id="4733c-105">The Resend Status Details page will then display information on the resend attempts made for this message.</span></span>  
  
 <span data-ttu-id="4733c-106">此报表才可用，如果选择了**重新发送 AS2 消息如果未收到 MDN**方作为相关方的 AS2 消息接收方属性中。</span><span class="sxs-lookup"><span data-stu-id="4733c-106">This report is only available if you have selected **Resend AS2 message if MDN not received** in the Party as AS2 Message Receiver properties for the related party.</span></span>  
  
 <span data-ttu-id="4733c-107">此报告显示在以下各页中对消息所做的重新尝试的相关信息：</span><span class="sxs-lookup"><span data-stu-id="4733c-107">The report displays information on the retry attempts made for the message on the following pages:</span></span>  
  
|<span data-ttu-id="4733c-108">第</span><span class="sxs-lookup"><span data-stu-id="4733c-108">Page</span></span>|<span data-ttu-id="4733c-109">显示的数据</span><span class="sxs-lookup"><span data-stu-id="4733c-109">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="4733c-110">**常规**</span><span class="sxs-lookup"><span data-stu-id="4733c-110">**General**</span></span>|<span data-ttu-id="4733c-111">当前发送尝试和重新发送配置的索引。</span><span class="sxs-lookup"><span data-stu-id="4733c-111">The index of the current send attempt as well as the resend configuration.</span></span>|  
|<span data-ttu-id="4733c-112">**重新发送历史记录**</span><span class="sxs-lookup"><span data-stu-id="4733c-112">**Resend History**</span></span>|<span data-ttu-id="4733c-113">消息发送尝试的历史记录。</span><span class="sxs-lookup"><span data-stu-id="4733c-113">A history of send attempts for the message.</span></span>|