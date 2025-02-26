# Generic Polygon Clipper (gpc) Revision History

## v2.33   
### 21st May 2014
- Fixed possible crash when multiple edges cross at the same location.
- Replaced fscanf calls with fscanf_s.

## v2.32   
### 17th Dec 2004
-   Fixed occasional memory leak occurring when processing some
    degenerate polygon arrangements.
-   Added explicit type casting to memory allocator in support of
    increased code portability.

## v2.31    
### 4th Jun 1999
-   Separated edge merging measure based on a user-defined GPC_EPSILON
    value from general numeric equality testing and ordering, which now
    uses direct arithmetic comparison rather an EPSILON based proximity
    test.
-   Fixed problem with numerical equality test during construction of
    local minima and scanbeam tables, leading to occasional crash.
    Fixed hole array memory leak in gpc_add_contour.
    Fixed uninitialised hole field bug in gpc_polygon_clip result.

## v2.30 
### 11th Apr 1999
-   Major re-write.
-   Minor API change: additional 'hole' array field added to gpc_polygon
    datatype to indicate which constituent contours are internal holes,
    and which form external boundaries.
-   Minor API change: additional 'hole' argument to gpc_add_contour
    to indicate whether the new contour is a hole or external contour.
-   Minor API change: additional parameter to gpc_read_polygon and
    gpc_write_polygon to indicate whether or not to read or write
    contour hole flags.
-   Fixed NULL pointer bug in add/merge left/right operations.
-   Fixed numerical problem in intersection table generation.
-   Fixed zero byte malloc problem.
-   Fixed problem producing occasional 2 vertex contours.
-   Added bounding box test optimisations.
-   Simplified edge bundle creation, detection of scanbeam internal
    edge intersections and tristrip scanbeam boundary code.
-   Renamed 'class' variable to be C++ friendly.

## v2.22   
### 17th Oct 1998
-   Re-implemented edge interpolation and intersection calculations
    to improve numerical robustness.
-   Simplified setting of GPC_EPSILON.

## v2.21
### 19th Aug 1998
-   Fixed problem causing occasional incorrect output when processing
    self-intersecting polygons (bow-ties etc).
-   Removed bug which may lead to non-generation of uppermost triangle
    in tristrip output.

## v2.20
### 26th May 1998
-   Major re-write.
-   Added exclusive-or polygon set operation.
-   Replaced table-based processing of edge intersections with
    rule-based system.
-   Replaced two-pass approach to scanbeam interior processing with
    single pass method.

## v2.10a  
### 14th May 1998
-   Minor bug-fixes to counter some v2.10 reliability problems.

## v2.10
###11th May 1998
-   Major re-write.
-   Incorporated edge bundle processing of AET to overcome coincident
    edge problems present in previous releases.
-   Replaced Vatti's method for processing scanbeam interior regions
    with an adapted version of the scanbeam boundary processing
    algorithm.

## v2.02
### 16th Apr 1998 (unreleased)
-   Fixed internal minimum vertex duplication in gpc_polygon_clip
    result.
-   Improved line intersection code discourage superfluous
    intersections near line ends. 
-   Removed limited precision number formatting in gpc_write_polygon.
-   Modification to allow subject or clip polygon to be reused as the
    result in gpc_polygon_clip without memory leakage.

## v2.01
### 23rd Feb 1998
-   Removed bug causing duplicated vertices in output polygon.
-   Fixed scanbeam table index overrun problem.

## v2.00
### 25th Nov 1997
-   Major re-write.
-   Replaced temporary horizontal edge work-around (using tilting)
    with true horizontal edge handling.
-   Trapezoidal output replaced by tristrips.
    gpc_op constants now feature a `GPC_' prefix.
-   Data structures now passed by reference to gpc functions.
-   Replaced AET search by proxy addressing in polygon table.
-   Eliminated most (all?) coincident vertex / edge crashes.

## v1.02
### 18th Oct 1997 (unreleased)
-   Significantly reduced number of mallocs in build_lmt. 
-   Scanbeam table now built using heapsort rather than insertion
    sort.
   
## v1.01
### 12th Oct 1997
-   Fixed memory leak during output polygon build in
    gpc_clip_polygon.
-   Removed superfluous logfile debug code.
-   Commented out malloc counts.
-   Added missing horizontal edge tilt-correction code in
    gpc_clip_polygon.
   
## v1.00
### 8th Oct 1997
-   First release.
