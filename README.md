# Havoc Vector Library
Gamesense LuaJIT API based Vector and Angle library.

Author credits:-
* Kessie Heldieheren
* halflifefan
* Localplayer
* sapphyrus

# Angle
## Create an angle
```lua
local my_angle = angle(0, 180, 0)
```

## Properties
**p**

Angle pitch.
***

**y**

Angle yaw.
***

**r**

Angle roll.
***

## Methods
```
:set(
	number|nil: p,
	number|nil: y,
	number|nil: r
): void
```
Set the angles. Nil will leave the angle unchanged.

*You may alternatively use `my_angle(p, y, r)` to set angles.*
***

```
:offset(
	number|nil: p,
	number|nil: y,
	number|nil: r
): angle_c
```
Offset the angles. 0 leaves the angle unchanged.
***

```
:clone(): angle_c
```
Clone the angle object.
***

```
:clone_offset(
	number|nil: p,
	number|nil: y,
	number|nil: r
): angle_c
```
Clone and offset the angles. 0 leaves the angle unchanged.
***

```
:clone_set(
	number|nil: p,
	number|nil: y,
	number|nil: r
): angle_c
```
Clone the angles and optionally override its coordinates. Nil values leave the angle unchanged.
***

```
:unpack(): number, number, number
```
Unpack the angles.
***

```
:nullify(): void
```
Set all angles to 0.
***

```
:round_zero(): void
```
Clamps the angles to whole numbers. Equivalent to "angle:round" with no precision.
***

```
:round(
	number|nil: precision
): void
```
Round the angles to a given precision. Nil is equivalent to 0 decimal place precision.
***

```
:round_base(
	number: base
): void
```
Clamps the angles to the nearest base.
***

```
:rounded_zero(): angle_c
```
Returns a new instance. Clamps the angles to whole numbers. Equivalent to "angle:round" with no precision.
***

```
:rounded(
	number|nil: precision
): angle_c
```
Returns a new instance. Round the angles to a given precision. Nil is equivalent to 0 decimal place precision.
***

```
:rounded_base(
	number: base
): angle_c
```
Returns a new instance. Clamps the angles to the nearest base.
***

```
:to_forward_vector(): vector_c
```
Returns a forward vector of the angle. Use this to convert an angle into a cartesian direction.
***

```
:to_backward_vector(): vector_c
```
Returns a backward vector of the angle. Use this to convert an angle into a cartesian direction.
***

```
:to_left_vector(): vector_c
```
Returns a left vector of the angle. Use this to convert an angle into a cartesian direction.
***

```
:to_right_vector(): vector_c
```
Returns a right vector of the angle. Use this to convert an angle into a cartesian direction.
***

```
:to_up_vector(): vector_c
```
Returns an up vector of the angle. Use this to convert an angle into a cartesian direction.
***

```
:to_down_vector(): vector_c
```
Returns a down vector of the angle. Use this to convert an angle into a cartesian direction.
***

# Vector
## Create a vector
```lua
local my_vector = vector(0, 100, 0)

-- Sets the vector's axes. Equivalent to :set.
my_vector(100, 0, 100)
```

## Properties
**x**

Vector X.
***

**y**

Vector Y.
***

**z**

Vector Z.
***

## Methods
```
:set(
	number|nil: x,
	number|nil: y,
	number|nil: z
): void
```
Set the vector. Nil will leave the axis unchanged.

*You may alternatively use `my_vector(x, y, z)` to set the axes.*
***

```
:clone_offset(
	number|nil: p_offset,
	number|nil: y_offset,
	number|nil: r_offset
): vector_c
```
Offset the vector. 0 leaves the vector unchanged.
***

```
:clone(): vector_c
```
Clone the vector object.
***

```
:clone_offset(
	number|nil: p_offset,
	number|nil: y_offset,
	number|nil: r_offset
): vector_c
```
Clone and offset the vector. 0 leaves the vector unchanged.
***

```
:clone_set(
	number|nil: p_new,
	number|nil: y_new,
	number|nil: r_new
): vector_c
```
Clone the vector and optionally override its coordinates. Nil values leave the vector unchanged.
***

```
:unpack(): number, number, number
```
Unpack the vector.
***

```
:nullify(): void
```
Set all vector to 0.
***

```
:round_zero(): void
```
Clamps the vector to whole numbers. Equivalent to "vector:round" with no precision.
***

```
:round(
	number|nil: precision
): void
```
Round the vector to a given precision. Nil is equivalent to 0 decimal place precision.
***

```
:round_base(
	number: base
): void
```
Clamps the vector to the nearest base.
***

```
:rounded_zero(): vector_c
```
Returns a new instance. Clamps the vector to whole numbers. Equivalent to "vector:round" with no precision.
***

```
:rounded(
	number|nil: precision
): vector_c
```
Returns a new instance. Round the vector to a given precision. Nil is equivalent to 0 decimal place precision.
***

```
:rounded_base(
	number: base
): vector_c
```
Returns a new instance. Clamps the vector to the nearest base.
***

```
:length2_squared(): number
```
Returns the vector's 2 dimensional length squared.
***

```
:length2(): number
```
Return's the vector's 2 dimensional length.
***

```
:length_squared(): number
```
Returns the vector's 3 dimensional length squared.
***

```
:length(): number
```
Return's the vector's 3 dimensional length.
***

```
:dot_product(): number
```
Returns the vector's dot product.
***

```
:cross_product(
	vector_c: b
): vector_c
```
Returns the vector's cross product.
***

```
:distance2(
	vector_c: destination
): number
```
Returns the 2 dimensional distance between the vector and another vector.
***

```
:distance(
	vector_c: destination
): number
```
Returns the 3 dimensional distance between the vector and another vector.
***

```
:distance_x(
	vector_c: destination
): number
```
Returns the X axis distance between the vector and another vector.
***

```
:distance_y(
	vector_c: destination
): number
```
Returns the X axis distance between the vector and another vector.
***

```
:distance_z(
	vector_c: destination
): number
```
Returns the Z axis distance between the vector and another vector.
***

```
:in_range(
	vector_c: destination,
	number: distance
): boolean
```
Returns true if the vector is within the given distance to another vector.
***

```
:normalize(): void
```
Normalize the vector.
***

```
normalized(): vector_c
```
Return a normalized clone of the vector.
***

```
normalized_length(): number
```
Returns the normalized length of a vector.
***

```
:to_screen(
	boolean: only_within_screen_boundary
): vector_c|nil
```
Returns a new 2 dimensional vector of the original vector when mapped to the screen, or nil if the vector is off-screen.

Pass true to only return a vector if the result of to_screen is within the game resolution.
***

```
:magnitude(): number
```
Returns the magnitude of the vector, use this to determine the speed of the vector if it's a velocity vector.
***

```
:angle_to(
	vector_c: destination
): angle_c
```
Returns the angle of the vector in regards to another vector.
***

```
:lerp(
	vector_c: destination
	number: percentage
): vector_c
```
Lerp the angle towards another vector.
***

```
:trace_line_to(
	vector_c: destination,
	number: skip_entindex
): number, number
```
Returns the result of client.trace_line between two vectors.
***

```
:trace_line_impact(
	vector_c: destination,
	number: skip_entindex
): vector_c
```
Trace line to another vector and returns the fraction, entity, and the impact point.
***

```
:trace_line_skip_indices(
	vector_c: destination,
	number|nil: max_traces,
	(function(number: eid): boolean): callback
): number, number, vector_c
```
Trace line to another vector, skipping any entity indices returned by the callback and returns the fraction, entity, and the impact point.

Callback should return true or false if the entity index given should be skipped or not skipped.
***

```
:trace_line_skip_class(
	vector_c: destination,
	table<any, string>: skip_classes,
	number: skip_distance
): 
```
Traces a line from source to destination and returns the fraction, entity, and the impact point.
***

```
:trace_bullet_to(
	vector_c: destination,
	number: eid
): number, number
```
Returns the result of client.trace_bullet between two vectors.
***

```
:closest_ray_point(
	vector_c: ray_start,
	vector_c: ray_end
): vector_c
```
Returns the vector of the closest point along a ray.
***

```
:ray_divided(
	vector_c: destination,
	number: ratio
): vector_c
```
Returns a point along a ray after dividing it.
***

```
:ray_segmented(
	vector_c: destination,
	number|nil: segments
): table<number, vector_c>
```
Returns a ray divided into a number of segments.
***

```
:ray(
	vector_c: destination,
	number|nil: total_segments
): vector_c, vector_c
```
Returns the best source vector and destination vector to draw a line on-screen using world-to-screen.

Allows you to draw lines whose points go off-screen.
***

```
:ray_intersects_smoke(
	vector_c: ray_end
): boolean
```
Returns true if the ray goes through a smoke. False if not.
***

```
:inside_polygon2(
	table<any, vector_c>: polygon
): boolean
```
Returns true if the vector lies within the boundaries of a given 2D polygon. The polygon is a table of vectors. The Z axis is ignored.
***

```
:draw_circle(
	number: radius,
	number: r,
	number: g,
	number: b,
	number: a,
	number: accuracy,
	number: width,
	number: outline,
	number: start_degrees,
	number: percentage
): void
```
Draws a world circle with an origin of the vector. Code credited to sapphyrus.
***

```
:min(
	number: value
): void
```
Performs math.min on the vector.
***

```
:max(
	number: value
): void
```
Performs math.max on the vector.
***

```
:minned(
	number: value
): vector_c
```
Performs math.min on the vector and returns the result.
***

```
:maxed(
	number: value
): vector_c
```
Performs math.max on the vector and returns the result.
***

## Functions
```
.draw_polygon(
	table<any, vector_c>: polygon,
	number: r,
	number: g,
	number: b,
	number: a,
	number: segments
): void
```
Draws a polygon to the screen.
***

```
.eye_position(
	number: eid
): vector_c
```
Returns the eye position of a player.
***

