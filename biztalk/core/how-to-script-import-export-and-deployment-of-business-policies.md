---
title: 如何编写脚本导入导出和部署业务策略 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- business rules, deploying
- policies, deploying
- business rules, exporting
- RuleSetDeploymentDriver
- business rules, importing
- Business Rules Framework, policies
- Business Rules Framework, business rules
- Business Rules Framework, code samples
- deploying, business rules
- Business Rules Framework, programming
ms.assetid: 333d37dc-e0ee-460c-922d-70eedf7b7ccb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fda67a54c63c8d1dd092e615b2057f00ad41bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254965"
---
# <a name="how-to-script-import-export-and-deployment-of-business-policies"></a><span data-ttu-id="aa8ee-102">如何编写导入导出和业务策略的部署脚本</span><span class="sxs-lookup"><span data-stu-id="aa8ee-102">How to Script Import-Export and Deployment of Business Policies</span></span>
<span data-ttu-id="aa8ee-103">本部分介绍如何以编程方式导入/导出和部署策略使用**RuleSetDeploymentDriver**。</span><span class="sxs-lookup"><span data-stu-id="aa8ee-103">This section describes how to programmatically import/export and deploy policies using **RuleSetDeploymentDriver**.</span></span>  
  
 <span data-ttu-id="aa8ee-104">以下示例将显示如何将策略导出到文件：</span><span class="sxs-lookup"><span data-stu-id="aa8ee-104">The following example shows how to export a policy to a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleExport  
{  
   class ExportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         if (args.Length != 3)  
            Console.WriteLine("Format: PolicyName MajorVersion MinorVersion");  
         else  
         {  
            string policyName = args[0];  
            int majorRev = Convert.ToInt16(args[1]);  
            int minorRev = Convert.ToInt16(args[2]);  
            RuleSetInfo rsi = new RuleSetInfo(policyName,majorRev,minorRev);  
            Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
            dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
                        string fileName = (rsi.Name + "-" + rsi.MajorRevision + "." + rsi.MinorRevision + ".xml");  
            dd.ExportRuleSetToFileRuleStore(rsi,fileName);  
         }  
      }  
   }  
}  
```  
  
 <span data-ttu-id="aa8ee-105">以下示例将显示如何从文件中导入策略并对其进行部署：</span><span class="sxs-lookup"><span data-stu-id="aa8ee-105">The following example shows how you can import and deploy a policy from a file.</span></span>  
  
```  
using System;  
using Microsoft.RuleEngine;  
using Microsoft.BizTalk.RuleEngineExtensions;  
namespace SimpleImport  
{  
   class ImportPolicy  
   {  
      [STAThread]  
      static void Main(string[] args)  
      {  
         String filename = args[0];  
         Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
         dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
         SqlRuleStore sqlRuleStore = (SqlRuleStore) dd.GetRuleStore();  
         FileRuleStore fileRuleStore = new FileRuleStore(filename);  
         RuleSetInfoCollection rsic = fileRuleStore.GetRuleSets(RuleStore.Filter.All);  
         foreach (RuleSetInfo rsi in rsic)  
         {  
            RuleSet ruleSet = fileRuleStore.GetRuleSet(rsi);  
            bool publishRuleSets = true;  
            sqlRuleStore.Add(ruleSet,publishRuleSets);  
            dd.Deploy(rsi);  
         }  
      }  
   }  
}    
```  
  
> [!NOTE]
>  <span data-ttu-id="aa8ee-106">代码假定对词汇没有依存关系；如果策略使用词汇，则必须首先导入这些词汇。</span><span class="sxs-lookup"><span data-stu-id="aa8ee-106">The code assumes no dependencies on vocabularies; if the policy uses vocabularies they must be imported first.</span></span>