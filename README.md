# go-polyline
Package `polyline` implements a Google Maps Encoding Polyline encoder and decoder.

## Encoding example

```go
func ExampleEncodeCoords() {
	coords := [][]float64{
		{38.5, -120.2},
		{40.7, -120.95},
		{43.252, -126.453},
	}
	fmt.Println(string(polyline.EncodeCoords(coords)))
	// Output: _p~iF~ps|U_ulLnnqC_mqNvxq`@
}
```

## Decoding example

```go
func ExampleDecodeCoords() {
	buf := []byte("_p~iF~ps|U_ulLnnqC_mqNvxq`@")
	coords, _, _ := polyline.DecodeCoords(buf)
	fmt.Println(coords)
	// Output: [[38.5 -120.2] [40.7 -120.95] [43.252 -126.453]]
}
```

## License

BSD-2-Clause
