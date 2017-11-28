---
title: "TestCrypto |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e9d3314b5564ab7619744e97f8e63df55683117
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testcrypto"></a><span data-ttu-id="a8ac2-102">TestCrypto</span><span class="sxs-lookup"><span data-stu-id="a8ac2-102">TestCrypto</span></span>
<span data-ttu-id="a8ac2-103">使用 TestCrypto 实用工具可以排除解密消息时的故障。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-103">You use the TestCrypto utility to troubleshoot failures in decrypting messages.</span></span> <span data-ttu-id="a8ac2-104">该实用工具指明解密是否失败。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-104">The utility indicates whether decryption fails.</span></span> <span data-ttu-id="a8ac2-105">如果解密成功，则该实用工具指明证书是什么，并显示解密的消息。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-105">If the decryption succeeds, the utility indicates what the certificate is, and displays the decrypted message.</span></span>  
  
 <span data-ttu-id="a8ac2-106">对只包含消息的加密部分而不包含未加密头的文件运行 TestCrypto。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-106">You run TestCrypto on a file that contains only the encrypted part of the message, without unencrypted headers.</span></span> <span data-ttu-id="a8ac2-107">通过探查传入消息或从 `MessageStorageIn` 中检索消息，可以将消息中加密的二进制大对象 (BLOB) 提取到文本文件中。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-107">Extract the encrypted binary large object (BLOB) from the message into a text file, either by sniffing the incoming message or by retrieving the message from `MessageStorageIn`.</span></span>  
  
 <span data-ttu-id="a8ac2-108">有关检索从消息详细信息`MessageStorageIn`，请参阅[GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-108">For more information about retrieving a message from `MessageStorageIn`, see [GetMessages Sample](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md).</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="a8ac2-109">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="a8ac2-109">Location in SDK</span></span>  
 <span data-ttu-id="a8ac2-110">\<*驱动器*> files\microsoft BizTalk\<版本 > RosettaNet\SDK 快捷键</span><span class="sxs-lookup"><span data-stu-id="a8ac2-110">\<*drive*>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK</span></span>  
  
## <a name="running-testcrypto"></a><span data-ttu-id="a8ac2-111">运行 TestCrypto</span><span class="sxs-lookup"><span data-stu-id="a8ac2-111">Running TestCrypto</span></span>  
  
#### <a name="to-run-testcrypto"></a><span data-ttu-id="a8ac2-112">运行 TestCrypto</span><span class="sxs-lookup"><span data-stu-id="a8ac2-112">To run TestCrypto</span></span>  
  
1.  <span data-ttu-id="a8ac2-113">单击**启动**，指向**所有程序**，指向**附件**，然后单击**命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-113">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="a8ac2-114">将移动到\<*驱动器*> files\microsoft BizTalk\<版本 > RosettaNet\SDK 快捷键。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-114">Move to \<*drive*>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK.</span></span>  
  
3.  <span data-ttu-id="a8ac2-115">在命令提示符处，键入**TestCrypto.exe\<文件名 >**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-115">At the command prompt, type **TestCrypto.exe \<filename>**, and then press ENTER.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8ac2-116">注释</span><span class="sxs-lookup"><span data-stu-id="a8ac2-116">Remarks</span></span>  
 <span data-ttu-id="a8ac2-117">如果该实用工具找到的证书不是所需的、有效的证书，或者该实用工具找不到证书，则解密失败。</span><span class="sxs-lookup"><span data-stu-id="a8ac2-117">Decryption fails if the certificate that the utility finds is not the required and valid certificate, or if the utility cannot find the certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ac2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ac2-118">See Also</span></span>  
 [<span data-ttu-id="a8ac2-119">实用程序</span><span class="sxs-lookup"><span data-stu-id="a8ac2-119">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)