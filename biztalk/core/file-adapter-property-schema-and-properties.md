---
title: 文件适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5671243de2ec3d3f97c8edf80d0de94a547301fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388045"
---
# <a name="file-adapter-property-schema-and-properties"></a><span data-ttu-id="8d1a4-102">文件适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="8d1a4-102">File adapter property schema and properties</span></span>
<span data-ttu-id="8d1a4-103">下表包含在文件适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-103">The following table contains the properties in the File adapter property schema.</span></span>  
  
 <span data-ttu-id="8d1a4-104">**Namespace**： http://schemas.microsoft.com/BizTalk/2003/file-properties</span><span class="sxs-lookup"><span data-stu-id="8d1a4-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span></span>  
  
|<span data-ttu-id="8d1a4-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="8d1a4-105">Name</span></span>|<span data-ttu-id="8d1a4-106">类型</span><span class="sxs-lookup"><span data-stu-id="8d1a4-106">Type</span></span>|<span data-ttu-id="8d1a4-107">Description</span><span class="sxs-lookup"><span data-stu-id="8d1a4-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="8d1a4-108">**CopyMode**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-108">**CopyMode**</span></span>|<span data-ttu-id="8d1a4-109">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8d1a4-109">xs:unsignedInt</span></span>|<span data-ttu-id="8d1a4-110">定义向文件中写入一条消息时要使用的复制模式。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-110">Defines the copy mode to use when writing a message to a file.</span></span> <span data-ttu-id="8d1a4-111">有效值为</span><span class="sxs-lookup"><span data-stu-id="8d1a4-111">Valid values are:</span></span><br /><br /> <span data-ttu-id="8d1a4-112">**追加 (0)。**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-112">**Append (0).**</span></span> <span data-ttu-id="8d1a4-113">如果它存在并且文件的末尾追加一条消息，该文件发送处理程序打开一个文件。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-113">The File send handler opens a file if it exists and appends a message to the end of the file.</span></span> <span data-ttu-id="8d1a4-114">如果文件不存在，则文件发送处理程序将创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-114">If the file does not exist, the File send handler creates a new file.</span></span><br /><br /> <span data-ttu-id="8d1a4-115">**创建新的 (1)。**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-115">**Create new (1).**</span></span> <span data-ttu-id="8d1a4-116">如果文件不存在，则文件发送处理程序创建一个新文件，并向其中写入。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-116">If a file does not exist, the File send handler creates a new file and writes to it.</span></span> <span data-ttu-id="8d1a4-117">如果该文件已存在，文件发送处理程序报告错误，然后按照发送端口的通用适配器重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-117">If the file already exists, the File send handler reports an error and then follows common adapter retry logic for send ports.</span></span> <span data-ttu-id="8d1a4-118">这是文件发送处理程序的默认复制模式。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-118">This is a default copy mode for the File send handler.</span></span><br /><br /> <span data-ttu-id="8d1a4-119">**覆盖 (2)。**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-119">**Overwrite (2).**</span></span> <span data-ttu-id="8d1a4-120">如果它存在并且覆盖其内容，该文件发送处理程序打开一个文件。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-120">The File send handler opens a file if it exists and overwrites its content.</span></span> <span data-ttu-id="8d1a4-121">如果文件不存在，则文件发送处理程序将创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-121">If the file does not exist, the File send handler creates a new file.</span></span>|  
|<span data-ttu-id="8d1a4-122">**AllowCacheOnWrite**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-122">**AllowCacheOnWrite**</span></span>|<span data-ttu-id="8d1a4-123">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="8d1a4-123">xs:Boolean</span></span>|<span data-ttu-id="8d1a4-124">定义文件适配器是否使用文件系统缓存到文件中写入消息时。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-124">Defines whether the File adapter uses file system caching when writing messages to a file.</span></span>|  
|<span data-ttu-id="8d1a4-125">**ReceivedFileName**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-125">**ReceivedFileName**</span></span>|<span data-ttu-id="8d1a4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d1a4-126">xs:string</span></span>|<span data-ttu-id="8d1a4-127">定义文件适配器从中读取消息的文件的完整名称。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-127">Defines the full name of the file from which the File adapter reads the message.</span></span>|  
|<span data-ttu-id="8d1a4-128">**FileCreationTime**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-128">**FileCreationTime**</span></span>|<span data-ttu-id="8d1a4-129">xs: datetime</span><span class="sxs-lookup"><span data-stu-id="8d1a4-129">xs:datetime</span></span>|<span data-ttu-id="8d1a4-130">定义写入该文件的时间到监视的文件的文件夹接收适配器。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-130">Defines the time that the file was written to the folder that is monitored by the File receive adapter.</span></span>|  
|<span data-ttu-id="8d1a4-131">**用户名**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-131">**Username**</span></span>|<span data-ttu-id="8d1a4-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d1a4-132">xs:string</span></span>|<span data-ttu-id="8d1a4-133">定义用于指定替代凭据时访问网络共享的帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-133">Defines the user name for the account used when specifying alternative credentials to access a network share.</span></span>|  
|<span data-ttu-id="8d1a4-134">**密码**</span><span class="sxs-lookup"><span data-stu-id="8d1a4-134">**Password**</span></span>|<span data-ttu-id="8d1a4-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d1a4-135">xs:string</span></span>|<span data-ttu-id="8d1a4-136">定义用于指定替代凭据时访问网络共享的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="8d1a4-136">Defines the password for the account used when specifying alternative credentials to access a network share.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d1a4-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d1a4-137">See Also</span></span>  
 [<span data-ttu-id="8d1a4-138">配置文件适配器</span><span class="sxs-lookup"><span data-stu-id="8d1a4-138">Configuring the File Adapter</span></span>](../core/configure-the-file-adapter.md)