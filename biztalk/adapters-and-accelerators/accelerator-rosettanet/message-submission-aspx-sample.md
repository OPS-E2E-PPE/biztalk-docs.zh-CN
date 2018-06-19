---
title: 消息提交 ASPX 示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8358f849-231f-432c-9fc2-6efdcf95580d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb7d90485014a62ed9010590d27a79ecd925c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207197"
---
# <a name="message-submission-aspx-sample"></a>消息提交 ASPX 示例
本主题提供可用于提交到专用的进程的服务内容的.aspx 代码示例。 你可以使用此.aspx 代码，而不是-的业务线 (LOB) 应用程序。  
  
## <a name="demonstrates"></a>演示  
 此代码演示如何调用`SubmitRNIF`方法来提交消息，其中包括：  
  
-   设置消息从应用程序的参数输入  
  
-   设置消息类别  
  
-   生成消息的合作伙伴接口过程 (PIP) 实例，如果提交的值为 null 或为空  
  
-   生成输入的附件文件数组和备注  
  
## <a name="example"></a>示例  
 此代码接受前端应用程序（如浏览器、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]® 或 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Word）的输入，并生成发起方专用流程可以使用的 XML 文档。  
  
 此 LOBWebApplication 实用程序包括下面的代码。 有关详细信息，请参阅[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)。  
  
```  
using System;  
using System.IO;  
using System.Text;  
using System.Data;  
using System.Drawing;  
using System.Collections;  
using System.ComponentModel;  
using System.Web;  
using System.Web.UI;  
using System.Web.SessionState;  
using System.Web.UI.WebControls;  
using System.Web.UI.HtmlControls;  
using Microsoft.Solutions.BTARN.SubmitRNIF;  
  
namespace Microsoft.Solutions.BTARN.SDK  
{  
      /// <summary>  
      /// Calls SubmitRNIF to submit service content to the BTARN private process.  
      /// </summary>  
      public class AspxLobApplication : System.Web.UI.Page  
      {  
            private void Page_Load(object sender, System.EventArgs e)  
            {  
                  Request.ValidateInput();  
  
                  string sPipCode=Request["PipCode"];  
                  string sPipVersion=Request["PipVersion"];  
                  string sPipInstanceID=Request["PipInstanceID"];  
                  string sPipCategory=Request["PipCategory"];  
                  string sPipSource=Request["PipSource"];  
                  string sPipDestination=Request["PipDestination"];  
                  string sFileName1=Request["FileName1"];  
                  string sFileName2=Request["FileName2"];  
                  string sRemark1=Request["Remark1"];  
                  string sRemark2=Request["Remark2"];  
                  string[] aInputFiles = new string[2];  
                  string[] aRemarks = new string[2];  
                  string sContent = Request["Textarea1"];  
  
                  SubmitRNIF.SubmitRNIF MessageSubmitter = new SubmitRNIF.SubmitRNIF();  
  
                  //The message category  
                  SubmitRNIF.SubmitRNIF.MessageCategory mc;  
                  if(sPipCategory.ToUpper() == "RESPONSE")   
                        mc=SubmitRNIF.SubmitRNIF.MessageCategory.Response;  
                  else  
                        mc=SubmitRNIF.SubmitRNIF.MessageCategory.Action;  
  
                  //Generate a PIP instance ID if the submitted value is null or empty  
                  if(sPipInstanceID.Length==0)  
                        sPipInstanceID=Guid.NewGuid().ToString();  
  
                  //Generate the input attachment files array and its associated remarks  
                  if(sFileName1!=null && sFileName1.Length>0) aInputFiles[0]=sFileName1;  
                  if(sFileName2!=null && sFileName2.Length>0) aInputFiles[1]=sFileName1;  
                  if(sRemark1!=null && sRemark1.Length>0) aRemarks[0]=sRemark1;  
                  if(sRemark2!=null && sRemark2.Length>0) aRemarks[1]=sRemark2;  
  
                  if(sFileName1==null && sFileName2==null)  
                        MessageSubmitter.SubmitMessage(mc, sPipSource, sPipDestination, sPipCode, sPipInstanceID, sPipVersion, sContent);  
                  else  
                        MessageSubmitter.SubmitMessage(mc, sPipSource, sPipDestination, sPipCode, sPipInstanceID, sPipVersion, sContent, aInputFiles);  
            }  
  
            #region Web Form Designer generated code  
...  
      }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)   
 [消息传送示例](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)