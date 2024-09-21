using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class IgaguriGenerator : MonoBehaviour
{
    public GameObject igaguriPrefab;

    void Update()
    {
        if (Input.GetMouseButtonDown(0))
        {
            GameObject igaguri = Instantiate(igaguriPrefab);

            Ray ray = Camera.main.ScreenPointToRay(Input.mousePosition);
            igaguri.GetComponent<IgaguriController>().Shoot(ray.direction * 2000);
        }
    }
}