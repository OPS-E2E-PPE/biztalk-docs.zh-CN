---
title: 重新发送状态详细信息报告 |Microsoft Docs
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
ms.openlocfilehash: 877e09fcbc2c2dc54b6c4f8bd7fb77827387b134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322107"
---
# <a name="resend-status-details-report"></a><span data-ttu-id="c47cb-102">重新发送状态详细信息报告</span><span class="sxs-lookup"><span data-stu-id="c47cb-102">Resend Status Details Report</span></span>
<span data-ttu-id="c47cb-103">此状态报告中显示的信息作为 AS2 接收方属性的参与方的参与方配置为未收到 MDN 时重新发送 AS2 消息时所做的重试尝试。</span><span class="sxs-lookup"><span data-stu-id="c47cb-103">This status report displays information on retry attempts made when the Party as AS2 Receiver properties of a party are configured to resend the AS2 message if an MDN is not received.</span></span>  
  
 <span data-ttu-id="c47cb-104">可通过上一条消息中 AS2/MDN 状态报告中，右键单击，然后单击显示此报告**查看可靠消息传送状态**。</span><span class="sxs-lookup"><span data-stu-id="c47cb-104">You display this report by right-clicking on a message in the AS2/MDN status report, and then clicking **View Reliable Messaging Status**.</span></span> <span data-ttu-id="c47cb-105">重新发送状态详细信息页将显示此消息所做的重新发送尝试的信息。</span><span class="sxs-lookup"><span data-stu-id="c47cb-105">The Resend Status Details page will then display information on the resend attempts made for this message.</span></span>  
  
 <span data-ttu-id="c47cb-106">此报告才可用，如果选择了**MDN 未收到时重新发送 AS2 消息**作为相关参与方的 AS2 消息接收方属性的参与方。</span><span class="sxs-lookup"><span data-stu-id="c47cb-106">This report is only available if you have selected **Resend AS2 message if MDN not received** in the Party as AS2 Message Receiver properties for the related party.</span></span>  
  
 <span data-ttu-id="c47cb-107">该报告显示所做的以下页面上的消息的重试尝试的信息：</span><span class="sxs-lookup"><span data-stu-id="c47cb-107">The report displays information on the retry attempts made for the message on the following pages:</span></span>  
  
|<span data-ttu-id="c47cb-108">第</span><span class="sxs-lookup"><span data-stu-id="c47cb-108">Page</span></span>|<span data-ttu-id="c47cb-109">显示数据</span><span class="sxs-lookup"><span data-stu-id="c47cb-109">Data Displayed</span></span>|  
|----------|--------------------|  
|<span data-ttu-id="c47cb-110">**常规**</span><span class="sxs-lookup"><span data-stu-id="c47cb-110">**General**</span></span>|<span data-ttu-id="c47cb-111">当前发送尝试重新发送配置的索引。</span><span class="sxs-lookup"><span data-stu-id="c47cb-111">The index of the current send attempt as well as the resend configuration.</span></span>|  
|<span data-ttu-id="c47cb-112">**重新发送历史记录**</span><span class="sxs-lookup"><span data-stu-id="c47cb-112">**Resend History**</span></span>|<span data-ttu-id="c47cb-113">历史记录的消息发送尝试次数。</span><span class="sxs-lookup"><span data-stu-id="c47cb-113">A history of send attempts for the message.</span></span>|