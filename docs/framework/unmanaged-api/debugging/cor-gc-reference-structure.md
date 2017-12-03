---
title: "COR_GC_REFERENCE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11be45743bd215315139fb77f016e85bc9b592c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corgcreference-structure"></a><span data-ttu-id="e4433-102">COR_GC_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="e4433-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="e4433-103">包含有关要进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="e4433-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4433-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4433-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="e4433-105">成员</span><span class="sxs-lookup"><span data-stu-id="e4433-105">Members</span></span>  
  
|<span data-ttu-id="e4433-106">成员</span><span class="sxs-lookup"><span data-stu-id="e4433-106">Member</span></span>|<span data-ttu-id="e4433-107">描述</span><span class="sxs-lookup"><span data-stu-id="e4433-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="e4433-108">指向句柄或对象所属的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="e4433-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="e4433-109">其值可能`null`。</span><span class="sxs-lookup"><span data-stu-id="e4433-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="e4433-110">ICorDebugValue 或 ICorDebugReferenceValue 接口对应于要进行垃圾回收的对象。</span><span class="sxs-lookup"><span data-stu-id="e4433-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="e4433-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举值，该值指示根来自何处。</span><span class="sxs-lookup"><span data-stu-id="e4433-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="e4433-112">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="e4433-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="e4433-113">要进行垃圾回收的对象有关的其他数据。</span><span class="sxs-lookup"><span data-stu-id="e4433-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="e4433-114">此信息取决于源的对象，如所示`type`字段。</span><span class="sxs-lookup"><span data-stu-id="e4433-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="e4433-115">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="e4433-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4433-116">备注</span><span class="sxs-lookup"><span data-stu-id="e4433-116">Remarks</span></span>  
 <span data-ttu-id="e4433-117">`type`字段是[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举值，该值指示引用来自何处。</span><span class="sxs-lookup"><span data-stu-id="e4433-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="e4433-118">特定`COR_GC_REFERENCE`值可以反映任何以下类型的托管对象：</span><span class="sxs-lookup"><span data-stu-id="e4433-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
-   <span data-ttu-id="e4433-119">从所有托管堆栈的对象 (`CorGCReferenceType.CorReferenceStack`)。</span><span class="sxs-lookup"><span data-stu-id="e4433-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="e4433-120">这包括实时引用在托管的代码中，以及由公共语言运行时创建的对象。</span><span class="sxs-lookup"><span data-stu-id="e4433-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="e4433-121">来自句柄表的对象 (`CorGCReferenceType.CorHandle*`)。</span><span class="sxs-lookup"><span data-stu-id="e4433-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="e4433-122">这包括的强引用 (`HNDTYPE_STRONG`和`HNDTYPE_REFCOUNT`) 和模块中的静态变量。</span><span class="sxs-lookup"><span data-stu-id="e4433-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="e4433-123">终结器队列中的对象 (`CorGCReferenceType.CorReferenceFinalizer`)。</span><span class="sxs-lookup"><span data-stu-id="e4433-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="e4433-124">终结器队列根对象，直到运行终结器。</span><span class="sxs-lookup"><span data-stu-id="e4433-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="e4433-125">`extraData`字段包含额外的数据，具体取决于引用的源 （或类型）。</span><span class="sxs-lookup"><span data-stu-id="e4433-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="e4433-126">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="e4433-126">Possible values are:</span></span>  
  
-   <span data-ttu-id="e4433-127">`DependentSource`。</span><span class="sxs-lookup"><span data-stu-id="e4433-127">`DependentSource`.</span></span> <span data-ttu-id="e4433-128">如果`type`是`CorGCREferenceType.CorHandleStrongDependent`，此字段是对象处于活动状态，如果根对象要进行垃圾回收在`COR_GC_REFERENCE.Location`。</span><span class="sxs-lookup"><span data-stu-id="e4433-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
-   <span data-ttu-id="e4433-129">`RefCount`。</span><span class="sxs-lookup"><span data-stu-id="e4433-129">`RefCount`.</span></span> <span data-ttu-id="e4433-130">如果`type`是`CorGCREferenceType.CorHandleStrongRefCount`，此字段是句柄的引用计数。</span><span class="sxs-lookup"><span data-stu-id="e4433-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
-   <span data-ttu-id="e4433-131">`Size`。</span><span class="sxs-lookup"><span data-stu-id="e4433-131">`Size`.</span></span> <span data-ttu-id="e4433-132">如果`type`是`CorGCREferenceType.CorHandleStrongSizedByref`，此字段是垃圾回收器为其计算对象根的对象树的最后一个大小。</span><span class="sxs-lookup"><span data-stu-id="e4433-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="e4433-133">请注意，此计算不一定最新。</span><span class="sxs-lookup"><span data-stu-id="e4433-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4433-134">要求</span><span class="sxs-lookup"><span data-stu-id="e4433-134">Requirements</span></span>  
 <span data-ttu-id="e4433-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4433-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4433-136">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4433-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4433-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4433-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4433-138">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4433-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4433-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4433-139">See Also</span></span>  
 [<span data-ttu-id="e4433-140">调试结构</span><span class="sxs-lookup"><span data-stu-id="e4433-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e4433-141">调试</span><span class="sxs-lookup"><span data-stu-id="e4433-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)