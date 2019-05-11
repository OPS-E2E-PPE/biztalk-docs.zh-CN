---
title: TestCrypto | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 881cd9ee8729a18f5829490e42c0795aa1267e43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280513"
---
# <a name="testcrypto"></a><span data-ttu-id="f1dd7-102">TestCrypto</span><span class="sxs-lookup"><span data-stu-id="f1dd7-102">TestCrypto</span></span>
<span data-ttu-id="f1dd7-103">TestCrypto 实用程序用于解决在解密消息的失败。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-103">You use the TestCrypto utility to troubleshoot failures in decrypting messages.</span></span> <span data-ttu-id="f1dd7-104">该实用工具指明解密是否失败。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-104">The utility indicates whether decryption fails.</span></span> <span data-ttu-id="f1dd7-105">如果解密成功，该实用工具指明证书是什么，并显示解密的消息。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-105">If the decryption succeeds, the utility indicates what the certificate is, and displays the decrypted message.</span></span>  
  
 <span data-ttu-id="f1dd7-106">包含仅加密的消息的一部分，而无需未加密的标头的文件运行 TestCrypto。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-106">You run TestCrypto on a file that contains only the encrypted part of the message, without unencrypted headers.</span></span> <span data-ttu-id="f1dd7-107">加密的二进制大型对象 (BLOB) 从消息中提取到文本文件中，通过探查传入消息或检索来自消息`MessageStorageIn`。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-107">Extract the encrypted binary large object (BLOB) from the message into a text file, either by sniffing the incoming message or by retrieving the message from `MessageStorageIn`.</span></span>  
  
 <span data-ttu-id="f1dd7-108">有关检索来自消息详细信息`MessageStorageIn`，请参阅[GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-108">For more information about retrieving a message from `MessageStorageIn`, see [GetMessages Sample](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="f1dd7-109">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="f1dd7-109">Location in SDK</span></span>  
 <span data-ttu-id="f1dd7-110">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="f1dd7-110">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-testcrypto"></a><span data-ttu-id="f1dd7-111">运行 TestCrypto</span><span class="sxs-lookup"><span data-stu-id="f1dd7-111">Running TestCrypto</span></span>  
  
#### <a name="to-run-testcrypto"></a><span data-ttu-id="f1dd7-112">若要运行 TestCrypto</span><span class="sxs-lookup"><span data-stu-id="f1dd7-112">To run TestCrypto</span></span>  
  
1.  <span data-ttu-id="f1dd7-113">单击**启动**，指向**所有程序**，指向**附件**，然后单击**命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-113">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="f1dd7-114">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-114">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span>  
  
3.  <span data-ttu-id="f1dd7-115">在命令提示符处，键入**TestCrypto.exe\<文件名\>**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-115">At the command prompt, type **TestCrypto.exe \<filename\>**, and then press ENTER.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1dd7-116">备注</span><span class="sxs-lookup"><span data-stu-id="f1dd7-116">Remarks</span></span>  
 <span data-ttu-id="f1dd7-117">如果找到该证书不是必需的和有效证书，或该实用工具找不到该证书将解密失败。</span><span class="sxs-lookup"><span data-stu-id="f1dd7-117">Decryption fails if the certificate that the utility finds is not the required and valid certificate, or if the utility cannot find the certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1dd7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1dd7-118">See Also</span></span>  
 [<span data-ttu-id="f1dd7-119">实用工具</span><span class="sxs-lookup"><span data-stu-id="f1dd7-119">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
