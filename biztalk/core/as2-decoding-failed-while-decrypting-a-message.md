---
title: 解密消息时，出现 AS2 解码失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78dea4d186de1b4cfe34998abc3f627eae0e8977
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528559"
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a><span data-ttu-id="2dedc-102">解密消息时，出现 AS2 解码失败</span><span class="sxs-lookup"><span data-stu-id="2dedc-102">AS2 decoding failed while decrypting a message</span></span>
## <a name="details"></a><span data-ttu-id="2dedc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2dedc-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2dedc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2dedc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2dedc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2dedc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2dedc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2dedc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2dedc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2dedc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2dedc-108">EDI</span><span class="sxs-lookup"><span data-stu-id="2dedc-108">EDI</span></span> |
|    <span data-ttu-id="2dedc-109">组件</span><span class="sxs-lookup"><span data-stu-id="2dedc-109">Component</span></span>    |                                       <span data-ttu-id="2dedc-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="2dedc-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="2dedc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2dedc-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="2dedc-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="2dedc-112">Message Text</span></span>   |                    <span data-ttu-id="2dedc-113">在解密消息时，出现 AS2 解码失败。</span><span class="sxs-lookup"><span data-stu-id="2dedc-113">AS2 decoding failed while decrypting a message.</span></span>                     |

## <a name="explanation"></a><span data-ttu-id="2dedc-114">解释</span><span class="sxs-lookup"><span data-stu-id="2dedc-114">Explanation</span></span>  
 <span data-ttu-id="2dedc-115">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解密 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="2dedc-115">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decrypt the AS2 message.</span></span> <span data-ttu-id="2dedc-116">如果解密过程中使用的证书无效、未存储在相应的位置或者与加密过程中使用的证书不匹配，都会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="2dedc-116">This can occur if the certificate used in the decryption process is not valid, is not stored in the appropriate location, or does not match the certificate used in the encryption process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2dedc-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="2dedc-117">User Action</span></span>  
 <span data-ttu-id="2dedc-118">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="2dedc-118">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="2dedc-119">验证 AS2 消息中的加密包装是否有效。</span><span class="sxs-lookup"><span data-stu-id="2dedc-119">Verify that the encryption wrapper in the AS2 message is valid.</span></span> <span data-ttu-id="2dedc-120">如果无效，请确定编码器对消息编码不正确的原因。</span><span class="sxs-lookup"><span data-stu-id="2dedc-120">If not, determine why the message was encoded improperly by the encoder.</span></span>  

- <span data-ttu-id="2dedc-121">验证加密过程中使用的公钥和解密过程中使用的私钥是否匹配。</span><span class="sxs-lookup"><span data-stu-id="2dedc-121">Verify that the public key used in the encryption process and the private key used in the decryption process match.</span></span>  

- <span data-ttu-id="2dedc-122">验证用于加密和解密的证书的“密钥用法”属性是否设置为“数据加密”。</span><span class="sxs-lookup"><span data-stu-id="2dedc-122">Verify that the Key Usage property of the certificate used for encryption and decryption is set to "data encipherment".</span></span>  

- <span data-ttu-id="2dedc-123">验证是否没有断开的中间证书颁发机构链。</span><span class="sxs-lookup"><span data-stu-id="2dedc-123">Verify that there is not a broken chain of intermediate certificate authorities.</span></span> <span data-ttu-id="2dedc-124">如果有，请删除旧证书，创建并使用新证书。</span><span class="sxs-lookup"><span data-stu-id="2dedc-124">If there is, delete the old certificate, and create and use a new certificate.</span></span>  

- <span data-ttu-id="2dedc-125">通过检查证书存储区中的过期日期来验证该证书是否过时（使用具有证书管理单元的 MMC）。</span><span class="sxs-lookup"><span data-stu-id="2dedc-125">Verify that the certificate has not timed out by checking its expiration date in the Certificates store (using MMC with a certificates snap-in.).</span></span>  

- <span data-ttu-id="2dedc-126">通过检查证书吊销列表来验证证书是否尚未被吊销。</span><span class="sxs-lookup"><span data-stu-id="2dedc-126">Verify that the certificate has not been revoked by checking the Certification Revocation List.</span></span> <span data-ttu-id="2dedc-127">（可以通过选中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台“常规 AS2”属性的“检查证书吊销列表”属性，让 BizTalk Server 自动检查此项。）</span><span class="sxs-lookup"><span data-stu-id="2dedc-127">(You can have BizTalk Server check this automatically by checking the Check Certification Revocation List property in the General AS2 properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.)</span></span>  

- <span data-ttu-id="2dedc-128">验证用于解密的证书是否存储在每台承载 MIME/SMIME 解码器管道的 BizTalk Server 上针对每个主机实例服务帐户的“当前用户\个人”存储区中。</span><span class="sxs-lookup"><span data-stu-id="2dedc-128">Verify that the certificate used for decryption is stored in the Current User\Personal store of each BizTalk server that hosts a MIME/SMIME decoder pipeline as each host instance service account.</span></span>
