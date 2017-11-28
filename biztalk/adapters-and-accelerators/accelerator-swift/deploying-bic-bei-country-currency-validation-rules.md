---
title: "部署 BIC 北路国家/地区货币验证规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f1786b37194db25f0e38db7491538857f3406b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a><span data-ttu-id="f6ea6-102">部署 BIC/北路/国家/地区/货币验证规则</span><span class="sxs-lookup"><span data-stu-id="f6ea6-102">Deploying BIC/BEI/Country/Currency Validation Rules</span></span>
<span data-ttu-id="f6ea6-103">**部署 BIC/北路/国家/地区/货币验证规则：**</span><span class="sxs-lookup"><span data-stu-id="f6ea6-103">**To deploy the BIC/BEI/Country/Currency Validation rules:**</span></span>  
  
1.  <span data-ttu-id="f6ea6-104">下面的一组策略，%程序 files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base 策略，也是泛型的且并不消息特定，需要为已发布和单独部署使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="f6ea6-104">The following set of policies, %program files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base Policies, which are generic and not message-specific, need to be published and deployed separately using the Business Rule Engine Deployment Wizard.</span></span>  
  
    -   <span data-ttu-id="f6ea6-105">MX_BIC_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-105">MX_BIC_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="f6ea6-106">MX_BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-106">MX_BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="f6ea6-107">MX_BEI_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-107">MX_BEI_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="f6ea6-108">MX_DBConnection_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-108">MX_DBConnection_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="f6ea6-109">MX_BICPlusIBAN_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-109">MX_BICPlusIBAN_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="f6ea6-110">MX_SEPA_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="f6ea6-110">MX_SEPA_Validation_Policy.xml</span></span>  
  
2.  <span data-ttu-id="f6ea6-111">在部署之前这些策略，MX_DBConnection_Master_Policy.xml 和 MX_BIC_Master_Policy.xml 应包含的数据库服务器名称和数据库名称的国家/地区/货币值存储位置。</span><span class="sxs-lookup"><span data-stu-id="f6ea6-111">Before deploying these policies, MX_DBConnection_Master_Policy.xml and MX_BIC_Master_Policy.xml should have the database server name and database name where the Country/Currency values have been stored.</span></span>  
  
3.  <span data-ttu-id="f6ea6-112">一旦主策略进行了修改，则发布所有策略使用业务规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="f6ea6-112">Once the master policies have been modified, publish all polices using the Business Rule Engine Deployment Wizard.</span></span> <span data-ttu-id="f6ea6-113">使用以下选项： 策略/词汇文件导入到数据库。</span><span class="sxs-lookup"><span data-stu-id="f6ea6-113">Use the following option: Import the policy/vocabulary file to database.</span></span>  
  
4.  <span data-ttu-id="f6ea6-114">单击程序，单击 BizTalk Server\<版本 >，单击业务规则编辑器，然后将部署发布了六个策略。</span><span class="sxs-lookup"><span data-stu-id="f6ea6-114">Click Programs, click BizTalk Server \<version>, click Business Rule Composer, and then deploy the six published polices.</span></span>