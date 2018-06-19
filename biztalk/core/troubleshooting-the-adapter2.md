---
title: 故障排除 Adapter2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991278813d2183795239d1a75c08e474b2f8159a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279189"
---
# <a name="troubleshooting-the-adapter"></a><span data-ttu-id="e21c4-102">故障排除适配器</span><span class="sxs-lookup"><span data-stu-id="e21c4-102">Troubleshooting the Adapter</span></span>
<span data-ttu-id="e21c4-103">本主题包含了一些信息，可帮助您识别和解决可能会在使用用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器时遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="e21c4-103">This topic contains information to help you identify and resolve issues that you might experience while you are using Microsoft BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a><span data-ttu-id="e21c4-104">无法在发送端口配置中使用通配符</span><span class="sxs-lookup"><span data-stu-id="e21c4-104">Cannot use wildcard characters in send port properties</span></span>  
 <span data-ttu-id="e21c4-105">用于 PeopleSoft Enterprise 的 BizTalk 适配器不支持在以下发送端口属性字段中使用通配符：</span><span class="sxs-lookup"><span data-stu-id="e21c4-105">BizTalk Adapter for PeopleSoft Enterprise does not support using wildcard characters in the following send port property fields:</span></span>  
  
-   <span data-ttu-id="e21c4-106">用户名</span><span class="sxs-lookup"><span data-stu-id="e21c4-106">Username</span></span>  
  
-   <span data-ttu-id="e21c4-107">App Server Path</span><span class="sxs-lookup"><span data-stu-id="e21c4-107">App Server Path</span></span>  
  
-   <span data-ttu-id="e21c4-108">Java_Home</span><span class="sxs-lookup"><span data-stu-id="e21c4-108">Java_Home</span></span>  
  
-   <span data-ttu-id="e21c4-109">People JAR Files</span><span class="sxs-lookup"><span data-stu-id="e21c4-109">People JAR Files</span></span>  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a><span data-ttu-id="e21c4-110">Get.xml 数据为空日期分配 0001-01-01 值</span><span class="sxs-lookup"><span data-stu-id="e21c4-110">Get.xml data assigns 0001-01-01 value for null dates</span></span>  
 <span data-ttu-id="e21c4-111">Get.xml 不正确地为空日期分配 0001-01-01 值。</span><span class="sxs-lookup"><span data-stu-id="e21c4-111">Get.xml incorrectly assigns 0001-01-01 value for null dates.</span></span> <span data-ttu-id="e21c4-112">如果希望使用空值替换 0001-01-01，则必须使用 BizTalk 映射器工具。</span><span class="sxs-lookup"><span data-stu-id="e21c4-112">You must use the BizTalk Mapper tool if you want to replace the 0001-01-01 with null.</span></span>  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a><span data-ttu-id="e21c4-113">创建和更新带有集合的属性失败</span><span class="sxs-lookup"><span data-stu-id="e21c4-113">Creating and updating properties with collections fails</span></span>  
 <span data-ttu-id="e21c4-114">使用 PeopleSoft 版本 8.17.02 的适配器时，适配器可以从 PeopleSoft 服务器中正确地读取数据。</span><span class="sxs-lookup"><span data-stu-id="e21c4-114">When using the Adapter with PeopleSoft version 8.17.02, the Adapter can read data from PeopleSoft server correctly.</span></span> <span data-ttu-id="e21c4-115">但是，创建和更新带有集合的属性将失败。</span><span class="sxs-lookup"><span data-stu-id="e21c4-115">However, creating and updating fails for properties with collections.</span></span> <span data-ttu-id="e21c4-116">这个已知 PeopleSoft 问题可能会在 PeopleSoft 将来的版本中得到解决。</span><span class="sxs-lookup"><span data-stu-id="e21c4-116">This is a known PeopleSoft issue that may be fixed in a future release of PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e21c4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e21c4-117">See Also</span></span>  
 [<span data-ttu-id="e21c4-118">故障排除 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="e21c4-118">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)