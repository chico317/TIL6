# TIL6 #python
-plotly
 *사용법
scatter([data_frame, x, y, color, symbol, …])
scatter_3d([data_frame, x, y, z, color, …])
scatter_polar([data_frame, r, theta, color, …])
scatter_ternary([data_frame, a, b, c, …])
scatter_mapbox([data_frame, lat, lon, …])
scatter_geo([data_frame, lat, lon, …])
line([data_frame, x, y, line_group, color, …])
line_3d([data_frame, x, y, z, color, …])
line_polar([data_frame, r, theta, color, …])
line_ternary([data_frame, a, b, c, color, …])
line_mapbox([data_frame, lat, lon, color, …])
line_geo([data_frame, lat, lon, locations, …])
area([data_frame, x, y, line_group, color, …])
bar([data_frame, x, y, color, facet_row, …])
timeline([data_frame, x_start, x_end, y, …])
bar_polar([data_frame, r, theta, color, …])
violin([data_frame, x, y, color, facet_row, …])
box([data_frame, x, y, color, facet_row, …])
strip([data_frame, x, y, color, facet_row, …])
histogram([data_frame, x, y, color, …])
pie([data_frame, names, values, color, …])
treemap([data_frame, names, values, …])
sunburst([data_frame, names, values, …])
funnel([data_frame, x, y, color, facet_row, …])
funnel_area([data_frame, names, values, …])
scatter_matrix([data_frame, dimensions, …])
parallel_coordinates([data_frame, …])
parallel_categories([data_frame, …])
choropleth([data_frame, lat, lon, …])
choropleth_mapbox([data_frame, geojson, …])
density_contour([data_frame, x, y, z, …])
density_heatmap([data_frame, x, y, z, …])
density_mapbox([data_frame, lat, lon, z, …])
imshow(img[, zmin, zmax, origin, labels, x, …])

# Graph Objects
1.2.1  Figure
Figure([data, layout, frames, skip_invalid])

1.2.2  Layout
Layout([arg, activeshape, angularaxis, …])

1.2.3  Simple Traces
Scatter([arg, cliponaxis, connectgaps, …])
Scattergl([arg, connectgaps, customdata, …])
Bar([arg, alignmentgroup, base, basesrc, …])
Pie([arg, automargin, customdata, …])
Heatmap([arg, autocolorscale, coloraxis, …])
Heatmapgl([arg, autocolorscale, coloraxis, …])
Image([arg, colormodel, customdata, …])
Contour([arg, autocolorscale, autocontour, …])
Table([arg, cells, columnorder, …])

1.2.4  Distribution Traces
Box([arg, alignmentgroup, boxmean, …])
Violin([arg, alignmentgroup, bandwidth, …])
Histogram([arg, alignmentgroup, autobinx, …])
Histogram2d([arg, autobinx, autobiny, …])
Histogram2dContour([arg, autobinx, …])

1.2.5  Finance Traces
Ohlc([arg, close, closesrc, customdata, …])
Candlestick([arg, close, closesrc, …])
Waterfall([arg, alignmentgroup, base, …])
Funnel([arg, alignmentgroup, cliponaxis, …])
Funnelarea([arg, aspectratio, baseratio, …])
Indicator([arg, align, customdata, …])

1.2.6  3D Traces –
Scatter3d([arg, connectgaps, customdata, …])
Surface([arg, autocolorscale, cauto, cmax, …])
Mesh3d([arg, alphahull, autocolorscale, …])
Cone([arg, anchor, autocolorscale, cauto, …])
Streamtube([arg, autocolorscale, cauto, …])
Volume([arg, autocolorscale, caps, cauto, …])
Isosurface([arg, autocolorscale, caps, …])

1.2.7  Map Traces
Scattergeo([arg, connectgaps, customdata, …])
Choropleth([arg, autocolorscale, coloraxis, …])
Scattermapbox([arg, below, connectgaps, …])
Choroplethmapbox([arg, autocolorscale, …])
Densitymapbox([arg, autocolorscale, below, …])

1.2.8  Specialized Traces
Scatterpolar([arg, cliponaxis, connectgaps, …])
Scatterpolargl([arg, connectgaps, …])
Barpolar([arg, base, basesrc, customdata, …])
Scatterternary([arg, a, asrc, b, bsrc, c, …])
Sunburst([arg, branchvalues, count, …])
Treemap([arg, branchvalues, count, …])
Sankey([arg, arrangement, customdata, …])
Splom([arg, customdata, customdatasrc, …])
Parcats([arg, arrangement, bundlecolors, …])
Parcoords([arg, customdata, customdatasrc, …])
Carpet([arg, a, a0, aaxis, asrc, b, b0, …])
Scattercarpet([arg, a, asrc, b, bsrc, …])
Contourcarpet([arg, a, a0, asrc, atype, …])


# 수익률 비교
기준점을 0으로 만들기위해서
df_1=df.set_index('date')-1
px.bar(df_1, x=df_1.index, y='GOOG')

# px.area 로 수익률 분포를 그립니다.
# facet_col 을 통해 서브플롯을 그릴 수 있습니다.
px.area(df_1,facet_col='company',facet_col_wrap=2)

# px.line 으로 전체 데이터의 수익률을 구합니다.
# hover_data={"date": "|%Y-%m-%d"} 로 시간을 표현할 수 있습니다.
px.line(df_1, facet_col='company')

# Range Slider와 함께 시계열 그래프 그리기
fig=px.line(df,x='date',y='AAPL')
fig.update_xaxes(rangeslider_visible=True)

# concat과 merge의 차이
concat :
axis=0 행을 기준으로 위아래로 같은 컬럼끼리 값을 이어 붙여 새로운 행을 만듦
axis=1 컬럼을 기준으로 인덱스가 같은 값을 옆으로 붙여 새로운 컬럼을 만듦
merge :
index 혹은 특정 컬럼 값을 기준으로 두 개의 데이터프레임을 연결

### axis = 0: 행을 의미 axis = 1: 컬럼을 의미!!!!
