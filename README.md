# Mapillary Image Fetcher

A web-based tool to fetch and visualize Mapillary street-level imagery within a specified bounding box.

<img width="1512" height="792" alt="Image" src="https://github.com/user-attachments/assets/2cc76de8-96f3-4d47-aaf3-deeb5a9966b2" />


## 🌐 Demo

[on GitHub Pages](https://mapconcierge.github.io/mapillarydatadownloader/)

## ✨ Features

- **Interactive Map**: Browse OpenStreetMap tiles with MapLibre GL JS
- **Token Verification**: Validate your Mapillary API access token before fetching data
- **Current View Fetching**: Automatically use the current map view as bounding box
- **Automatic Area Adjustment**: Handles Mapillary's 0.01 square degree limit with auto-adjustment
- **Pagination Support**: Fetches all available images across multiple API pages
- **Visual Display**: Shows image locations as blue circle markers on the map
- **Image Preview**: Click any marker to view the street-level image in a popup
- **GeoJSON Export**: Download all fetched data as a timestamped GeoJSON file
- **Responsive Design**: Works on desktop and mobile devices

## 🚀 Getting Started

### 1. Get a Mapillary Access Token

1. Sign up or log in at [Mapillary](https://www.mapillary.com/)
2. Go to [Mapillary Developer Dashboard](https://www.mapillary.com/dashboard/developers)
3. Create a new application or use an existing one
4. Copy your Client Token (format: `MLY|...|...`)

### 2. Use the Application

1. Open the application in your web browser
2. Paste your Mapillary access token into the input field
3. Click **"Verify Token"** to validate your credentials
4. Pan and zoom the map to your desired area
5. Click **"Fetch Images in Current View"** to retrieve Mapillary images
6. Click on blue markers to view street-level images
7. Use **"Download GeoJSON"** to save the data locally

## 📋 Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Valid Mapillary API access token
- Internet connection

## 🔧 Technical Details

### Technologies Used

- **MapLibre GL JS v4**: Interactive map rendering
- **OpenStreetMap**: Base map tiles
- **Mapillary API v4**: Street-level imagery data

### API Specifications

- **Endpoint**: `https://graph.mapillary.com/images`
- **Authentication**: OAuth token via `Authorization` header
- **Bounding Box Limit**: Maximum 0.01 square degrees
- **Fields Retrieved**: `id`, `computed_geometry`, `captured_at`, `compass_angle`, `thumb_2048_url`

### GeoJSON Output Format
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [longitude, latitude]
      },
      "properties": {
        "id": "image_id",
        "captured_at": "2024-01-01T12:00:00Z",
        "thumb_2048_url": "https://...",
        "compass_angle": 90.5
      }
    }
  ]
}
```

## 🎯 Use Cases

- Urban planning and analysis
- Street infrastructure mapping
- Change detection over time
- Computer vision dataset creation
- Route planning and documentation
- Research and academic projects

## ⚠️ Limitations

- Maximum bounding box area: 0.01 square degrees (~1.1km × 1.1km at equator)
- Areas larger than the limit are automatically adjusted from the center
- API rate limits apply based on your Mapillary account tier
- Requires active internet connection

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs or issues
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🔗 Related Links

- [Mapillary API Documentation](https://www.mapillary.com/developer/api-documentation)
- [MapLibre GL JS Documentation](https://maplibre.org/maplibre-gl-js/docs/)
- [OpenStreetMap](https://www.openstreetmap.org/)

## 📧 Support

For questions or support, please open an issue on the GitHub repository.

---

Made with ❤️ using MapLibre GL JS and Mapillary API
