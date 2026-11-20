# Improve-videos
algoritmo práctico para mejorar videos (por ejemplo, para YouTube)
def mejorar_video(video, metricas):
    problemas = []

    if metricas["ctr"] < metricas["ctr_objetivo"]:
        problemas.append({
            "tipo": "atraccion",
            "accion": "probar titulo_y_miniatura",
            "prioridad": 1
        })

    if metricas["retencion_30s"] < metricas["retencion_30s_objetivo"]:
        problemas.append({
            "tipo": "gancho",
            "accion": "recortar_intro_y_adelantar_valor",
            "prioridad": 2
        })

    if metricas["puntos_abandono"]:
        problemas.append({
            "tipo": "estructura",
            "accion": "editar_secciones_con_mayor_caida",
            "prioridad": 3
        })

    if metricas["engagement"] < metricas["engagement_objetivo"]:
        problemas.append({
            "tipo": "participacion",
            "accion": "anadir_pregunta_y_llamada_a_la_accion",
            "prioridad": 4
        })

    return sorted(problemas, key=lambda x: x["prioridad"])
