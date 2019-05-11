---
title: 验证 AS2 消息时出错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d797989290b0211e619e0c5ae4b4408cda02c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360068"
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a><span data-ttu-id="e933c-102">验证 AS2 消息时出错</span><span class="sxs-lookup"><span data-stu-id="e933c-102">An error occurred when validating an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="e933c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e933c-103">Details</span></span>  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e933c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e933c-104">Product Name</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| <span data-ttu-id="e933c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e933c-105">Product Version</span></span> |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    <span data-ttu-id="e933c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e933c-106">Event ID</span></span>     |                                                           -                                                           |
|  <span data-ttu-id="e933c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e933c-107">Event Source</span></span>   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e933c-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e933c-108">EDI</span></span>                 |
|    <span data-ttu-id="e933c-109">组件</span><span class="sxs-lookup"><span data-stu-id="e933c-109">Component</span></span>    |                                                      <span data-ttu-id="e933c-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="e933c-110">AS2 Engine</span></span>                                                       |
|  <span data-ttu-id="e933c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e933c-111">Symbolic Name</span></span>  |                                                           -                                                           |
|  <span data-ttu-id="e933c-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="e933c-112">Message Text</span></span>   | <span data-ttu-id="e933c-113">验证 AS2 消息时出错。</span><span class="sxs-lookup"><span data-stu-id="e933c-113">An error occurred when validating an AS2 message.</span></span> <span data-ttu-id="e933c-114">请确保使用的证书不具有已超时或被吊销。</span><span class="sxs-lookup"><span data-stu-id="e933c-114">Make sure the certificates used have not timed out or been revoked.</span></span> |

## <a name="explanation"></a><span data-ttu-id="e933c-115">解释</span><span class="sxs-lookup"><span data-stu-id="e933c-115">Explanation</span></span>  
 <span data-ttu-id="e933c-116">此错误/警告/信息事件表明 AS2 接收管道或 AS2 发送管道无法验证 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="e933c-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not validate the AS2 message.</span></span> <span data-ttu-id="e933c-117">如果签名验证过程中使用的证书无效、 未存储在相应的位置，或与签名过程中使用的证书不匹配，这可能发生。</span><span class="sxs-lookup"><span data-stu-id="e933c-117">This can occur if the certificate used in the signature verification process is not valid, is not stored in the appropriate location, or does not match the certificate used in the signing process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e933c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e933c-118">User Action</span></span>  
 <span data-ttu-id="e933c-119">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="e933c-119">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="e933c-120">验证 AS2 消息中的签名包装有效。</span><span class="sxs-lookup"><span data-stu-id="e933c-120">Verify that the signature wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="e933c-121">如果没有，确定为什么消息错误签名的编码器。</span><span class="sxs-lookup"><span data-stu-id="e933c-121">If not, determine why the message was signed improperly by the encoder.</span></span>  

- <span data-ttu-id="e933c-122">验证签名过程中使用的私钥和签名验证过程中使用的公钥匹配。</span><span class="sxs-lookup"><span data-stu-id="e933c-122">Verify that the private key used in the signing process and the public key used in the signature verification process match.</span></span>  

- <span data-ttu-id="e933c-123">验证用于签名和签名验证的证书的密钥用法属性设置为"数据加密"。</span><span class="sxs-lookup"><span data-stu-id="e933c-123">Verify that the Key Usage property of the certificate used for signing and signature verification is set to "data encipherment".</span></span>  

- <span data-ttu-id="e933c-124">验证是否没有断开的中间证书颁发机构链。</span><span class="sxs-lookup"><span data-stu-id="e933c-124">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="e933c-125">如果有，请删除旧证书，创建并使用新证书。</span><span class="sxs-lookup"><span data-stu-id="e933c-125">If there is, delete the old certificate, and create and use a new certificate.</span></span>  

- <span data-ttu-id="e933c-126">通过检查证书存储区中的过期日期来验证该证书是否过时（使用具有证书管理单元的 MMC）。</span><span class="sxs-lookup"><span data-stu-id="e933c-126">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  

- <span data-ttu-id="e933c-127">通过检查证书吊销列表来验证证书是否尚未被吊销。</span><span class="sxs-lookup"><span data-stu-id="e933c-127">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="e933c-128">（可以通过选中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台“常规 AS2”属性的“检查证书吊销列表”属性，让 BizTalk Server 自动检查此项。）</span><span class="sxs-lookup"><span data-stu-id="e933c-128">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  

- <span data-ttu-id="e933c-129">验证用于签名验证的证书存储在本地计算机 / 其他人将存储的每个 BizTalk server 承载 MIME/SMIME 解码器管道的每个主机实例服务帐户。</span><span class="sxs-lookup"><span data-stu-id="e933c-129">Verify that the certificate used for signature verification is stored in the Local computer/Other People store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>
