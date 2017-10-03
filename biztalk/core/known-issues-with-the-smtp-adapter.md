---
title: "已知问题的 SMTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b530e39e-c4e7-4b98-be0b-4d02eb2e8dc7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8691da466c2915cee4b8746e20a0d5a96d82d81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-smtp-adapter"></a><span data-ttu-id="a78e4-102">SMTP 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="a78e4-102">Known Issues with the SMTP Adapter</span></span>
<span data-ttu-id="a78e4-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="a78e4-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="a78e4-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="a78e4-104">Known Issues</span></span>  
  
#### <a name="error-in-the-biztalk-server-application-log-if-emailbodytextcharset-is-not-defined"></a><span data-ttu-id="a78e4-105">未定义 EmailBodyTextCharset 时 BizTalk Server 应用程序日志中的错误</span><span class="sxs-lookup"><span data-stu-id="a78e4-105">Error in the BizTalk Server Application Log if EmailBodyTextCharset is not defined</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a78e4-106">问题</span><span class="sxs-lookup"><span data-stu-id="a78e4-106">Problem</span></span>  
 <span data-ttu-id="a78e4-107">如果未定义 EmailBodyTextCharset 并且在 BizTalk Server 应用程序日志中生成如下错误，则在 BizTalk Server 应用程序日志中将生成错误。</span><span class="sxs-lookup"><span data-stu-id="a78e4-107">Errors are generated in the BizTalk Server application log if the EmailBodyTextCharset is not defined and an error similar to the followign is generated in the BizTalk Server application log:</span></span>  
  
```  
Event Type:Error  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:5754  
Date:9/1/2006  
Time:10:50:11 AM  
User:N/A  
Computer:TEST2006  
Description:  
A message sent to adapter "SMTP" on send port "TIE Test_1.0.0.0_TIE_Test.TieRespTest_Email_Port_4f4f8f4101d5615a" with URI "mailto:approver@BTS2006.com" is suspended.   
Error details: Unknown Error Description   
MessageId: {3F12EBE1-1CDA-44FE-85FE-C2CB8228F287}  
InstanceID: {0616E750-22FF-4380-B413-C94718421340}  
```  
  
##### <a name="cause"></a><span data-ttu-id="a78e4-108">原因</span><span class="sxs-lookup"><span data-stu-id="a78e4-108">Cause</span></span>  
 <span data-ttu-id="a78e4-109">必须为设置一个值**EmailBodyTextCharset**参数。</span><span class="sxs-lookup"><span data-stu-id="a78e4-109">A value must be set for the **EmailBodyTextCharset** parameter.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a78e4-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="a78e4-110">Resolution</span></span>  
 <span data-ttu-id="a78e4-111">为指定值**EmailBodyTextCharset**参数。</span><span class="sxs-lookup"><span data-stu-id="a78e4-111">Specify a value for the **EmailBodyTextCharset** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a78e4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a78e4-112">See Also</span></span>  
 [<span data-ttu-id="a78e4-113">故障排除 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="a78e4-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)