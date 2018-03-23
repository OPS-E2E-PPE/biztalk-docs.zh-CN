---
title: BizTalk 消息正文元素编码无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a><span data-ttu-id="47ec2-102">BizTalk 消息正文元素编码无效</span><span class="sxs-lookup"><span data-stu-id="47ec2-102">BizTalk message body element encoding is invalid</span></span>
## <a name="details"></a><span data-ttu-id="47ec2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="47ec2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47ec2-104">產品名稱</span><span class="sxs-lookup"><span data-stu-id="47ec2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="47ec2-105">產品版本</span><span class="sxs-lookup"><span data-stu-id="47ec2-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="47ec2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="47ec2-106">Event ID</span></span>|<span data-ttu-id="47ec2-107">0</span><span class="sxs-lookup"><span data-stu-id="47ec2-107">0</span></span>|  
|<span data-ttu-id="47ec2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="47ec2-108">Event Source</span></span>|<span data-ttu-id="47ec2-109">0</span><span class="sxs-lookup"><span data-stu-id="47ec2-109">0</span></span>|  
|<span data-ttu-id="47ec2-110">组件</span><span class="sxs-lookup"><span data-stu-id="47ec2-110">Component</span></span>|<span data-ttu-id="47ec2-111">0</span><span class="sxs-lookup"><span data-stu-id="47ec2-111">0</span></span>|  
|<span data-ttu-id="47ec2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="47ec2-112">Symbolic Name</span></span>|<span data-ttu-id="47ec2-113">0</span><span class="sxs-lookup"><span data-stu-id="47ec2-113">0</span></span>|  
|<span data-ttu-id="47ec2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="47ec2-114">Message Text</span></span>|<span data-ttu-id="47ec2-115">BizTalk 消息正文元素编码“{0}”无效。</span><span class="sxs-lookup"><span data-stu-id="47ec2-115">BizTalk message body element encoding "{0}" is invalid.</span></span> <span data-ttu-id="47ec2-116">预期编码:"xml"，"base64"，"十六进制"或"string"</span><span class="sxs-lookup"><span data-stu-id="47ec2-116">Expected encoding: "xml", "base64", "hex", or "string"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47ec2-117">解释</span><span class="sxs-lookup"><span data-stu-id="47ec2-117">Explanation</span></span>  
 <span data-ttu-id="47ec2-118">此错误表示对传出消息使用了 BizTalk 正文模板选项，但是，为 BizTalk 正文指定的编码类型无效。</span><span class="sxs-lookup"><span data-stu-id="47ec2-118">This error indicates the use of the BizTalk body template option for the outgoing messages; however, the encoding type specified for the BizTalk body is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47ec2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="47ec2-119">User Action</span></span>  
 <span data-ttu-id="47ec2-120">使用以下过程配置编码类型。</span><span class="sxs-lookup"><span data-stu-id="47ec2-120">Use the following procedure to configure the encoding type.</span></span>  
  
#### <a name="to-configure-the-encoding-type"></a><span data-ttu-id="47ec2-121">配置编码类型的步骤</span><span class="sxs-lookup"><span data-stu-id="47ec2-121">To configure the encoding type</span></span>  
  
1.  <span data-ttu-id="47ec2-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="47ec2-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="47ec2-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="47ec2-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="47ec2-124">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="47ec2-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="47ec2-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="47ec2-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="47ec2-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="47ec2-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="47ec2-127">在端口 **类型** 列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="47ec2-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="47ec2-128">单击 **配置**。</span><span class="sxs-lookup"><span data-stu-id="47ec2-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="47ec2-129">在**WCF [***传输类型***] 传输属性**对话框中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="47ec2-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="47ec2-130">在 **出站 WCF 消息正文** 部分中，单击 **模板-指定通过模板内容** 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="47ec2-130">In the **Outbound WCF message body** section, click the **Template – Content specified by template** radio button.</span></span> <span data-ttu-id="47ec2-131">在 **XML** 文本框中，BizTalk 正文的格式应为</span><span class="sxs-lookup"><span data-stu-id="47ec2-131">In the **XML** text box, the format of the BizTalk body should be</span></span>   
    <span data-ttu-id="47ec2-132">\<**bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="[xml&#124;base64&#124;十六进制&#124;字符串]"/** \> (区分大小写，编码的有效值为 xml&#124;base64&#124;十六进制&#124;字符串)</span><span class="sxs-lookup"><span data-stu-id="47ec2-132">\<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span></span>